# REDIS

Redis stands for :
  REmote
  DIrectory
  Server

Its an in-memory data structure store, used as a database, cache and message broker.

Redis is not a distributed cache. 
If you need an off-the-shelf distributed store, Redis is probably not a good option. You will be better served by Cassandra, Riak, MongoDB, Couchbase, Aerospike, MySQL Cluster, Oracle NoSQL, etc ... However, if you want to build your own specialized system, Redis is an excellent component to build upon.

## Install

#### Docker
TO pull redis image: `docker pull redis`
TO run redis container: `docker run --name my-redis -p 6379:6379 -d redis`
TO go inside redis container :`docker exec -it my-redis bash`

## Commands
- TO open redis cli : `redis-cli`
- TO check if the connection from cli with server is alive : `ping`, reply will be pong
- to close the connectiion : `quit`
- to set key value pair `set foo 100`
- to get value of the key : `get foo`, will return value if exists else nil
- to increment a number `INCR foo`
- to decrement a number `DECR foo`
- to check if key exists `EXISTS foo`, returns 0/1, 1:exists
- to delete a key `DEL foo`
- to clean the cache `flushall`
- to set the expiry time of key `EXPIRE foo 100`, foo will expire in 100 secs
- to get the remaining amount of secs left for a key `TTL foo`
- to set the key value along with expiration time `SETEX key seconds value`
- to persist a key having expired time `PERSIST key`
- to set multiple values `MSET key1 value1 key2 value2 ...`
- to rename a key `RENAME oldKayName newKeyName`
- to push a list of elements `LPUSH key values...`
- to print the list `LRANGE key start end`, start and end are the index, end as -1 means end index of list
- to get the length of list `LLEN key`
- to remove from start/end of list `LPOP/RPOP`
- to insert before any element `LINSERT listName BEFORE elemName`
- to add into set `SADD `
- to check if value present in set `SISMEMBER`
- to print the members of set `SMEMBERS`
- to get the number of elements in set `SCARD`
- to move lements from one set to another `SMOVE`
- to remove from set `SREM`
- to print the key of any type if present `KEYS pattern`
- to find the datatype of key `TYPE key`

## Datatypes supported by REDIS

String

List : collections of string elements sorted according to the order of insertion. They are basically linked lists.

SET : collections of unique, unsorted string elements.

SortedSet : similar to Sets but where every string element is associated to a floating number value, called score. The elements are always taken sorted by their score, so unlike Sets it is possible to retrieve a range of elements (for example you may ask: give me the top 10, or the bottom 10).

Hashes : which are maps composed of fields associated with values. Both the field and the value are strings. This is very similar to Ruby or Python hashes.

Bitarrays : (or simply bitmaps): it is possible, using special commands, to handle String values like an array of bits: you can set and clear individual bits, count all the bits set to 1, find the first set or unset bit, and so forth.

HyperLogLogs: this is a probabilistic data structure which is used in order to estimate the cardinality of a set. Don't be scared, it is simpler than it seems... See later in the HyperLogLog section of this tutorial.

Streams: append-only collections of map-like entries that provide an abstract log data type. 

# Spring Boot Cache

## 1. Configure the Redis Template


To set a specific cache set the property `spring.cache.type` in application properties.  
EG : `spring.cache.type=redis`


### Dependency 

```xml
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-redis</artifactId>
		</dependency>
```

### Redis template based

#### Configuration

Redis connections are obtained using LettuceConnectionFactory or JedisConnectionFactory. Lettuce and Jedis are Java Redis clients. Spring Boot 2.0 uses Lettuce by default.

#### Using Lettuce Connection Factory

```java
@Configuration
public class RedisConfiguration {
	
	@Autowired
	LettuceConnectionFactory connfactory;

	@Bean
	public RedisTemplate<String, Object> redisTemplate() {
		final RedisTemplate<String, Object> redisTemplate = new RedisTemplate<String, Object>();
		redisTemplate.setKeySerializer(new StringRedisSerializer());
		redisTemplate.setValueSerializer(new StudentSerializer());
		redisTemplate.setConnectionFactory(connfactory);
		return redisTemplate;
	}
}


```

Spring Boot 2.0 starter spring-boot-starter-data-redis resolves Lettuce by default. Spring provides LettuceConnectionFactory to get connections. To get pooled connection factory we need to provide commons-pool2 on the classpath. To work with Lettuce we need following Maven dependencies.
```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-data-redis</artifactId>
</dependency>		
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-pool2</artifactId>
</dependency> 
```
To configure Lettuce pool we need to use spring.redis.* prefix with Lettuce pool connection properties. Find the Lettuce pool sample configurations. 

```properties
application.properties
spring.redis.host=localhost 
spring.redis.port=6379
spring.redis.password= 

spring.redis.lettuce.pool.max-active=7 
spring.redis.lettuce.pool.max-idle=7
spring.redis.lettuce.pool.min-idle=2
spring.redis.lettuce.pool.max-wait=-1ms  
spring.redis.lettuce.shutdown-timeout=200ms 
```
We can override default Redis host, port and password configurations. Use max-wait a negative value if we want to block indefinitely.



#### Using Jedis  Connection Factory
By default Spring Boot 2.0 starter spring-boot-starter-data-redis uses Lettuce. To use Jedis we need to exclude Lettuce dependency and include Jedis. Find the Maven dependencies to use Jedis.
```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-data-redis</artifactId>
  <exclusions>
    <exclusion>
	 <groupId>io.lettuce</groupId>
	 <artifactId>lettuce-core</artifactId>
    </exclusion>
  </exclusions>		    
</dependency>		
<dependency>
  <groupId>redis.clients</groupId>
  <artifactId>jedis</artifactId>
</dependency> 
```
jedis dependency will automatically resolve commons-pool2 on the classpath. 
To configure Jedis pool we need to use spring.redis.* prefix with Jedis pool connection properties. Find the Jedis pool sample configurations. 
```
application.properties
spring.redis.host=localhost 
spring.redis.port=6379
spring.redis.password= 

spring.redis.jedis.pool.max-active=7 
spring.redis.jedis.pool.max-idle=7
spring.redis.jedis.pool.min-idle=2
spring.redis.jedis.pool.max-wait=-1ms
```

```java

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.data.redis.connection.RedisConnectionFactory;
import org.springframework.data.redis.connection.jedis.JedisConnectionFactory;
import org.springframework.data.redis.core.RedisTemplate;
import org.springframework.data.redis.core.StringRedisTemplate;
import com.concretepage.bean.Person;
import redis.clients.jedis.JedisPoolConfig;
@Configuration
@ComponentScan("com.concretepage")
public class RedisConfig {
	@Bean
	public RedisConnectionFactory redisConnectionFactory() {
		JedisPoolConfig poolConfig = new JedisPoolConfig();
		poolConfig.setMaxTotal(5);
		poolConfig.setTestOnBorrow(true);
		poolConfig.setTestOnReturn(true);
		
		JedisConnectionFactory connectionFactory = new JedisConnectionFactory(poolConfig);
		connectionFactory.setUsePool(true);
		connectionFactory.setHostName("localhost");
		connectionFactory.setPort(6379);
		
		return connectionFactory;
	}
	@Bean
	public RedisTemplate<String, Person> redisTemplate() {
		RedisTemplate<String, Person> redisTemplate = new RedisTemplate<>();
		redisTemplate.setConnectionFactory(redisConnectionFactory());
		redisTemplate.setEnableTransactionSupport(true);
		return redisTemplate;
	}
	@Bean
	public StringRedisTemplate stringRedisTemplate() {
		StringRedisTemplate stringRedisTemplate = new StringRedisTemplate(redisConnectionFactory());
		stringRedisTemplate.setEnableTransactionSupport(true);
		return stringRedisTemplate;
	}	
} 

```

### Sample Code using rest template
https://github.com/himkak/springBootRedis
transaction and synchronization not yet implemented.


#### @Transactional support

RedisTemplate does not provide transaction support (Spring @Transactional annotation) by default. To enable it we need to call its method setEnableTransactionSupport(true)

## 2. Spring Caching using cache Abstraction 

The Spring caching service is an abstraction (not a cache implementation) and requires the use of actual storage to store the cache data,that is, the abstraction frees you from having to write the caching logic but does not provide the actual data store. This abstraction is materialized by the org.springframework.cache.Cache and org.springframework.cache.CacheManager interfaces.

Spring provides a few implementations of that abstraction: JDK java.util.concurrent.ConcurrentMap based caches, Ehcache 2.x, Gemfire cache, Caffeine, and JSR-107 compliant caches (such as Ehcache 3.x).

It supports JSR-107

1)add dependency spring-boot-starter-cache
2)add annotation enableCaching
3)The caching Object class should implement serializable
4)Use @cacheable annotation, which states, cache the result of this method.

![Spring cache abstraction annotation](https://github.com/himkak/notes/blob/master/Cache/SpringCacheAbstractionAnnotations.PNG)

accountId1
### @cacheable 
It is generally used over get method. 
When the method is invoked, 
	if the object doesnt exists in cache, the method is executed, the returned object is saved in cache. 
	If the object exists, the object is pulled from cache and returned and method is not executed.
The TTL is set only when the object is saved.

### @cachePut 
This annotation is used to save the object.
It is executed every time, the object being returned is saved in cache. Even if the object already resides in cache.
The TTL is set every time.


### @cacheEvict 
to remove the object from cache

Spring's Cache Abstraction does not support saving list of objects behavior out-of-the-box. 
https://github.com/spring-projects/spring-framework/issues/19777

However, it does not mean it is not possible; it's just a bit more work to support the desired behavior.
https://github.com/jxblum/spring-gemfire-tests/blob/master/src/test/java/org/spring/cache/CachingCollectionElementsIndividuallyWithConcurrentMapTest.java


### Sample code
https://github.com/himkak/SpringBootCache
Able to save the List, as object, and doesnt provides to fetch sublist.
TODO set the TTL

## 3. JCache

![Spring cache abstraction annotation vs JCache annotations](https://github.com/himkak/notes/blob/master/Cache/SpringVsJCacheAnnotations.PNG)

# Caches Comparison

## Security, encryption

## Scalability


## Required use cases:

- Save a list of students of a school with elements already sorted
- Set expiry time for the list
- refresh the expiry time of list on every fetch
- fetch elements of students of a specific school on index from 0 to 20
- fetch elements from 20 to 40...
- Delete the list of a specific school



# References
- redis crash course : https://www.youtube.com/watch?v=Hbt56gFj998
- Docker redis: https://hub.docker.com/_/redis/
- Redis Datatypes: https://redis.io/topics/data-types-intro
- Redis for windows download : https://github.com/dmajkic/redis/downloads
- Spring boot cacheing documentation : https://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-caching.html#boot-features-caching
- RedisTemplate operations : https://docs.spring.io/spring-data/redis/docs/current/api/org/springframework/data/redis/core/RedisTemplate.html
- Spring cache abstraction : https://docs.spring.io/spring/docs/4.3.15.RELEASE/spring-framework-reference/html/cache.html
- Spring Boot Redis using cache Abstraction: https://www.youtube.com/watch?v=6uWU3gDhZk4
- Spring cache abstraction saving list of object : https://stackoverflow.com/questions/33657881/what-strategies-exist-for-using-spring-cache-on-methods-that-take-an-array-or-co
- Spring Cache Abstraction : https://docs.spring.io/spring/docs/current/spring-framework-reference/integration.html#cache
- Caching with Spring: Advanced Topics and Best Practices : https://www.youtube.com/watch?v=SpQzWtqulhM
