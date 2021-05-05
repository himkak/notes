# SYSTEM DESIGN

Investing in scaling before it is needed is generally not a smart business proposition; however, some forethought into the design can save valuable time and resources in the future.

## Theory

<details>
<summary> Basics
</summary>

### System Design Basics

- https://www.youtube.com/watch?v=uaD8ugY9C_c : How to prepare for System Design Interview | 4 Essential Tips

- https://www.cronj.com/blog/system-designing-basics/ : system design basics

- https://coursehunters.online/t/educative-io-design-gurus-grokking-the-system-design-interview-part-5/584 : Detailed overview of all the jargons   

- https://www.freecodecamp.org/news/systems-design-for-interviews/amp/

- https://lethain.com/introduction-to-architecting-systems-for-scale/

- https://github.com/donnemartin/system-design-primer#system-design-topics-start-here : system design prep github page, by a FB SE (*****)

- https://tianpan.co/notes/2016-02-13-crack-the-system-design-interview : Crack the System Design Interview




### Key Characteristics of Distributed Systems

- https://www.youtube.com/watch?v=Y6Ev8GIlbxc : Distributed Systems in One Lesson by Tim Berglund

- https://learning.oreilly.com/videos/distributed-systems-in/9781491924914 : Distributed Systems in One Lesson

#### Scaling

- http://highscalability.com/blog/2010/12/1/8-commonly-used-scalable-system-design-patterns.html

- http://highscalability.com/blog/2010/11/24/great-introductory-video-on-scalability-from-harvard-compute.html

- https://www.lecloud.net/search/scalability

- http://highscalability.com/blog/2012/9/19/the-4-building-blocks-of-architecting-systems-for-scale.html

- https://www.youtube.com/watch?v=-W9F__D3oY4 : CS75 (Summer 2012) Lecture 9 Scalability Harvard Web Development David Malan



</details>

<details>
<summary> Network
</summary>

### OSI Model

- https://www.youtube.com/watch?v=vv4y_uOneC0

### Content Delivery Network
A CDN is a third-party service that acts like a cache for your servers. Sometimes, web applications can be slow for users in a particular region if your servers are located only in another region. A CDN has servers all around the world, meaning that the latency to a CDN's servers will almost always be far better than the latency to your servers. Two of the most popular CDNs are Cloudflare and Google Cloud CDN.

- https://www.youtube.com/watch?v=Bsq5cKkS33I : What is a Content Delivery Network (CDN)?



### DNS
Short for Domain Name System, it describes the entities and protocols involved in the translation from domain names to IP Addresses. Typically, machines make a DNS query to a well known entity which is responsible for returning the IP address (or multiple ones) of the requested domain name in the response.

- https://www.youtube.com/watch?v=JkEYOt08-rU : DNS (Domain Name System) - Explained , Types of Domain Name Servers | How DNS works | TechTerms

- https://www.youtube.com/watch?v=dh406O2v_1c : What happens when type google.com into your browser address box and hit enter?


### DMZ

- https://www.youtube.com/watch?v=dqlzQXo1wqo

In computer networks, a DMZ (demilitarized zone), also sometimes known as a perimeter network or a screened subnetwork, is a physical or logical subnet that separates an internal local area network (LAN) from other untrusted networks -- usually the internet. External-facing servers, resources and services are located in the DMZ. Therefore, they are accessible from the internet, but the rest of the internal LAN remains unreachable. This provides an additional layer of security to the LAN as it restricts a hacker's ability to directly access internal servers and data via the internet.

Any service provided to users on the public internet should be placed in the DMZ network. Some of the most common of these services include web servers and proxy servers, as well as servers for email, domain name system (DNS), File Transfer Protocol (FTP) and voice over IP (VoIP).

### NAT

- https://www.youtube.com/watch?v=FTUV0t6JaDA

Network Address Translation (NAT) is the process where a network device, usually a firewall, assigns a public address to a computer (or group of computers) inside a private network. The main use of NAT is to limit the number of public IP addresses an organization or company must use, for both economy and security purposes.

The most common form of network translation involves a large private network using addresses in a private range (10.0.0.0 to 10.255.255.255, 172.16.0.0 to 172.31.255.255, or 192.168.0 0 to 192.168.255.255). The private addressing scheme works well for computers that only have to access resources inside the network, like workstations needing access to file servers and printers. Routers inside the private network can route traffic between private addresses with no trouble. However, to access resources outside the network, like the Internet, these computers have to have a public address in order for responses to their requests to return to them. This is where NAT comes into play.

- https://whatismyipaddress.com/nat

</details>


<details>
<summary> Data Flow
</summary>

### Load Balancing

A type of reverse proxy that distributes traffic across servers. Load balancers can be found in many parts of a system, from the DNS layer all the way to the database layer.

- https://www.youtube.com/watch?v=7LMaAVwZE2c : Load Balancing | What are Load Balancers?

- https://www.educative.io/courses/grokking-the-system-design-interview/3jEwl04BL7Q 

#### Algos
- https://www.youtube.com/watch?v=iqOTT7_7qXY

- Round Robin
- weighted round robin : u have to provide the weight of each server
- Least connections
- Weighted Least connections
- Random

#### L3

- To distribute between different data centres.

#### L4
- https://www.nginx.com/resources/glossary/layer-4-load-balancing/

- For Internet traffic specifically, a Layer 4 load balancer bases the load-balancing decision on the source and destination IP addresses and ports recorded in the packet header, without considering the contents of the packet.

#### L7
- Layer 7 load balancers base their routing decisions on various characteristics of the HTTP header and on the actual contents of the message, such as the URL, the type of data (text, video, graphics), or information in a cookie.
- They serve as reverse proxy

- https://www.nginx.com/resources/glossary/layer-7-load-balancing/


#### Two-Tier Load Balancing Scheme

### Proxies

#### Forward Proxy

A server that sits between a client and servers and acts on behalf of the client, typically used to mask the client's identity (IP address). Note that forward proxies are often referred to as just proxies.

- https://www.youtube.com/watch?v=ozhe__GdWC8&t=241s : Proxy vs. Reverse Proxy (Explained by Example)


#### Reverse Proxy
A server that sits between clients and servers and acts on behalf of the servers, typically used for logging, load balancing, or caching.

In computer networks, a reverse proxy is a type of proxy server that retrieves resources on behalf of a client from one or more servers. These resources are then returned to the client, appearing as if they originated from the proxy server itself. Unlike a forward proxy, which is an intermediary for its associated clients to contact any server, a reverse proxy is an intermediary for its associated servers to be contacted by any client. In other words, a proxy acts on behalf of the client(s), while a reverse proxy acts on behalf of the server(s).


- https://www.youtube.com/watch?v=S8J2fkN2FeI : Load Balancer vs Reverse Proxy (Explained by Example)


### API Gateway 

- https://microservices.io/patterns/apigateway.html
- https://www.youtube.com/watch?v=vHQqQBYJtLI

**Functionalities provided by API Gateway**

- Security : Authentication & Authorization
- Routing
- Protocol Translation
- Audit

- It acts as the single entryway into a system allowing multiple APIs or microservices to act cohesively and provide a uniform experience to the user. 
- The most important role the API gateway plays is ensuring reliable processing of every API call.

![API GW](https://github.com/himkak/notes/blob/master/SystemDesign/ApiGw.png)

**Problems it solves**
- How to support different clients
	- Different clients need different data
	- Network performance is different for different types of clients
- The number of service instances and their locations (host+port) changes dynamically
- Services might use a diverse set of protocols, some of which might not be web friendly

**Solution**
- Translates from a “standard” public web-friendly API protocol to whatever protocols are used internally
- Simplifies the client by moving logic for calling multiple services from the client to API gateway
- Insulates the clients from how the application is partitioned into microservices
- Insulates the clients from the problem of determining the locations of service instances
- Provides the optimal API for each client

#### ZUUL API GATEWAY

- https://www.youtube.com/watch?v=sPgwbt7iREk


### Streaming
In networking, it usually refers to the act of continuously getting a feed of information from a server by keeping an open connection between the two machines or processes.




</details>

<details>
<summary> Data Storage
</summary>

# Data Storage

### SAN

A Storage Area Network (SAN) is a specialized, high-speed network that provides block-level network access to storage. SANs are typically composed of hosts, switches, storage elements, and storage devices that are interconnected using a variety of technologies, topologies, and protocols. SANs may also span multiple sites.

A SAN presents storage devices to a host such that the storage appears to be locally attached. This simplified presentation of storage to a host is accomplished through the use of different types of virtualization.

### SSD & HD

https://www.crucial.com/articles/about-ssd/ssd-vs-hdd#

- ssd : Solid State Drive

## Relational DB

### Federation

Federation (or functional partitioning) splits up databases by function. For example, instead of a single, monolithic database, you could have three databases: forums, users, and products, resulting in less read and write traffic to each database and therefore less replication lag. Smaller databases result in more data that can fit in memory, which in turn results in more cache hits due to improved cache locality. With no single central master serializing writes you can write in parallel, increasing throughput.

### Indexes

### Redundancy and Replication

### SQL vs. NoSQL

### CAP Theorem
Stands for Consistency, Availability, Partition tolerance. In a nutshell, this theorem states that any distributed system can only achieve 2 of these 3 properties. Furthermore, since almost all useful systems do have network-partition tolerance, it's generally boiled down to: Consistency vs. Availability; pick one.

One thing to keep in mind is that some levels of consistency are still achievable with high availability, but strong consistency is much harder.


http://ksat.me/a-plain-english-introduction-to-cap-theorem in layman terms by comparing with real world

- https://codahale.com/you-cant-sacrifice-partition-tolerance/

### PACELC

- https://pusher.com/sessions/meetup/the-realtime-guild/realtime-ish-shared-state-latency-vs-consistency 
- https://pbs.twimg.com/media/D850vcJUIAA1Ygy.jpg 

### Sharding Relational DB

- https://www.citusdata.com/blog/2017/08/09/principles-of-sharding-for-relational-databases/


## NoSql DBs

- https://www.youtube.com/watch?v=qI_g07C_Q5I


### Consistent Hashing  

Problem : In a distributed system, when we add or remove servers. If we use hashing, hasd-code to identify the server, the hash-code of all the data will change, when we add or remove server.

A type of hashing that minimizes the number of keys that need to be remapped when a hash table gets resized. It's often used by load balancers to distribute traffic to servers; it minimizes the number of requests that get forwarded to different servers when new servers are added or when existing servers are brought down.

- https://www.youtube.com/watch?v=tHEyzVbl4bg

- https://www.youtube.com/watch?v=UU_JG8Uujvo 

- https://www.toptal.com/big-data/consistent-hashing   

- https://www.ably.io/blog/implementing-efficient-consistent-hashing   

- https://www.youtube.com/watch?v=QWeO2OB40VY&list=PLq9MXGH7Fkt-2j8wwR2hUeTlSoFiGQDsJ&index=5&t=13s

- https://en.wikipedia.org/wiki/Category:Hashing

- https://www.youtube.com/watch?v=apHAqUG3Pi8

- https://medium.com/system-design-blog/consistent-hashing-b9134c8a9062

- http://tom-e-white.com/2007/11/consistent-hashing.html : also contains sample implementation, using TreeMap

- https://www.ably.io/blog/implementing-efficient-consistent-hashing/


### Caching 

#### Redis

- https://github.com/himkak/notes/tree/master/Redis 

#### Cache Eviction Policy

##### LRU
The backing data structure is : HashMap for get, put and delete in O(1), backed by doubly linked list to maintain the priority order to identify the least recently used entity.
- https://www.youtube.com/watch?v=DUbEgNw-F9c (video)(Bit of distributed cache more of LRU)
- https://www.youtube.com/watch?v=S6IfqDXWa10&t=585s (video)
- https://www.learn4master.com/data-structures/hashtable/leetcode-lru-cache-solution-in-java (Implementation in java)
- https://www.quora.com/How-are-linked-lists-good-for-LRU-caches
##### TTL

#### Distributed Cache

**MemCached**


### Data Partitioning


#### Cassandra
- https://github.com/himkak/notes/blob/master/DB/cassandra/Cassandra.md

- https://docs.datastax.com/en/archived/cassandra/3.0/cassandra/architecture/archTOC.html

#### HBase

- good for big data (TBs or PBs)
- good for random reads and writes

- https://www.youtube.com/watch?v=hs8QnQvwyCM
- https://www.youtube.com/watch?v=2Ci_QxJ1kiE
- https://www.youtube.com/watch?v=VRD775iqAko

### Graph DB

- Alternative to rest or replacament of REST
- provides bi-directional streaming
- 

#### Neo4j

- https://neo4j.com/graphacademy/online-training/introduction-to-neo4j/part-1/


### Time series Database

**Key features**
- Data is immutable. Once the data is inserted, it will not be changed
- Query is done on time range. In comparison to relational db where query is done on match basis (which might be using indexes). So relational DB doesnt fits well for managing time series database.
- Every row in timeseries DB represents a time window

- https://www.youtube.com/watch?v=HB9bG3Qcvq8 : What is a Time Series Database?
- https://www.youtube.com/watch?v=SgD3RD2Shg4 : Time Series Databases in the Upside-down Internet 

- 

### Event Store
- Databse optimized for storing events

### Comparison of Databases

- https://www.youtube.com/watch?v=QlqylUeqeis : Cassandra vs MongoDB vs HBase | Difference Between Popular NoSQL Databases | Edureka

- https://www.youtube.com/watch?v=v5e_PasMdXc : How to Choose the Right Database? - MongoDB, Cassandra, MySQL, HBase - Frank Kane
	- If I have huge amount of data and want to scale in future, then go for NoSql
	- If My Data is not very much organized, then Go for NoSql.
	
![Which DB to prefer](https://github.com/himkak/notes/blob/master/SystemDesign/WhichDbToPrefer.png)

- https://www.youtube.com/watch?v=KWOSGVtHWqA : AWS re:Invent 2017: [REPEAT] Which Database to Use When? (DAT310-R)

#### Which Database to use when
- Points to be considered:
	- shape
		- row store : RDBMS
		- column store : cassandra
		- key-value store : redis
		- Document store : Mongo
		- Graph store
		- Time series store
		- unstructured store
	- size
		- Is the size of data bounded(if the size of data has limits) or unbounded(if the size of data has no limits)
		- Is the data partitionable or monolithic 
	- compute
		- compute functions
		- throughput, latency, change rate, rate of ingestion
	- Do you need managed DB service or are you going to manage it by yourself
	- is the data transactional
	

### Polyglot persistence
- Polyglot persistence is the concept of using different data storage technologies to handle different data storage needs within a given enterprise and even software application.

#### Points to be considered to decide the Database

- shape

![Data shape](https://github.com/himkak/notes/blob/master/SystemDesign/DB_Consideration_Shape.PNG)

- size

![Data size](https://github.com/himkak/notes/blob/master/SystemDesign/DB_Consideration_Size.PNG)

- computational requirements for the data

![Data compute](https://github.com/himkak/notes/blob/master/SystemDesign/DB_Consideration_Compute.PNG)

- 
![DB types with behaviour](https://github.com/himkak/notes/blob/master/SystemDesign/DbTypesWithBehaviour.PNG)

- 
![Relational DBs behaviour](https://github.com/himkak/notes/blob/master/SystemDesign/RelationalDbsBehaviour.PNG)

### Database Lock

### Searching

- https://www.youtube.com/watch?v=KyCYyoGusqs

#### Inverted / reverese index
- https://www.geeksforgeeks.org/inverted-index/

#### Elastic Search

- uses apache lucene

### Transations

#### Relational DB

##### ACID Transaction 
A type of database transaction that has four important properties:

**Atomicity**: The operations that constitute the transaction will either all succeed or all fail. There is no in-between state.  
**Consistency**: The transaction cannot bring the database to an invalid state. After the transaction is committed or rolled back, the rules for each record will still apply, and all future transactions will see the effect of the transaction. Also named Strong Consistency.  
**Isolation**: The execution of multiple transactions concurrently will have the same effect as if they had been executed sequentially.  
**Durability**: Any committed transaction is written to non-volatile storage. It will not be undone by a crash, power loss, or network partition.  



#### Distributed Transactions


#### 2 Phase Commit

- https://codahale.com/you-cant-sacrifice-partition-tolerance/

- https://stackoverflow.com/questions/7389382/two-phase-commit

### OLAP

### OLTP

### Sharding
Sometimes called data partitioning, sharding is the act of splitting a database into two or more pieces called shards and is typically done to increase the throughput of your database. Popular sharding strategies include:

Sharding based on a client's region
Sharding based on the type of data (e.g: user data gets stored in one shard, payments data gets stored in another shard)
Sharding based on the hash of a column (only for structured data)

- http://www.25hoursaday.com/weblog/2009/01/16/BuildingScalableDatabasesProsAndConsOfVariousDatabaseShardingSchemes.aspx

### AWS S3

</details>

<details>
<summary> Data Computation
</summary>

### MapReduce
A popular framework for data processing at a very large scale by splitting the work into as many sub-tasks as needed and processing those in parallel on a big cluster of machines. It is comprised of 2 main steps: Map and Reduce. The map step takes the input and its output will further get passed onto reducers. The output of the reducers get concatenated into the final result.

### Async processing

</details>


<details>
<summary> Distributed System Management
</summary>

# Distributed System Management

### Leader Election
The process by which nodes in a cluster (for instance, servers in a set of servers) elect a so-called "leader" amongst them, responsible for the primary operations of the service that these nodes support. When correctly implemented, leader election guarantees that all nodes in the cluster know which one is the leader at any given time and can elect a new leader if the leader dies for whatever reason.

### Consensus Algorithm
A type of complex algorithms used to have multiple entities agree on a single data value, like who the "leader" is amongst a group of machines. Two popular consensus algorithms are Paxos and Raft.

### ZooKeeper
ZooKeeper is a strongly consistent, highly available key-value store. It's often used to store important configuration or to perform leader election.



</details>

<details>
<summary> NFRs
</summary>

# NFRs

### Monitoring 

#### APIs 

### Fault tolerant 

### Latency
The time it takes for a certain operation to complete in a system. Most often this measure is a time duration, like milliseconds or seconds. 



</details>




<details>
<summary> Encryption
</summary>

## Encryption

### SHA
Short for "Secure Hash Algorithms", the SHA is a collection of cryptographic hash functions used in the industry. These days, SHA-3 is a popular choice to use in a system.


</details>


<details>
<summary> Jargons
</summary>

### SLA
Short for "service-level agreement", an SLA is a collection of guarantees given to a customer by a service provider. SLAs typically make guarantees on a system's availability, amongst other things. SLAs are made up of one or multiple SLOs.

### SLO
Short for "service-level objective", an SLO is a guarantee given to a customer by a service provider. SLOs typically make guarantees on a system's availability, amongst other things. SLOs constitute an SLA.

</details>


<details>
<summary> Communication
</summary>

### Long-Polling vs WebSockets vs Server-Sent Events

- https://www.educative.io/courses/grokking-the-system-design-interview/gx7wZzWn5Vj

### Polling
The act of fetching a resource or piece of data regularly at an interval to make sure your data is not too stale.


#### JMS 	

### Eventing System


### Kafka

- https://github.com/himkak/notes/tree/master/Kafka 


### HTTP Security Authentication Authorization

- https://app.pluralsight.com/library/courses/oauth2-json-web-tokens-openid-connect-introduction/table-of-contents?aid=7010a000002BWq6AAG : oauth2, jwt, openId

- https://app.pluralsight.com/library/courses/web-security-owasp-top10-big-picture/table-of-contents : owasp top 10

- https://restfulapi.net/security-essentials/

- https://apifriends.com/api-security/api-security-best-practices/

- https://medium.com/swlh/3-ways-to-secure-your-web-api-for-different-situations-8d5cd4762ab3#:~:text=OAuth,endpoint%20for%20the%20login%20process.

- https://dzone.com/refcardz/oauth-patterns-and-anti-patterns?chapter=1



#### JWT
- https://dzone.com/articles/are-you-using-jwts-for-user-sessions-in-the-correc?fromrel=true

- https://www.youtube.com/watch?v=soGRyl9ztjI   (Introduction: what is session token, issues with session token and session-id, what is jwt token oh high level and how it solves the issue)  
- https://www.youtube.com/watch?v=_XbXkVdoG_0    (JWT structure)   

#### OAUTH  
Used to access a resource via service on behalf of the owner of the resource.  
https://www.youtube.com/watch?v=3pZ3Nh8tgTE   

- https://dzone.com/storage/assets/14464316-dzone-refcard-347-oauth-patterns-anti-patterns-202.pdf
- https://dzone.com/articles/deep-dive-to-oauth20-amp-jwt-part-2-oauth20?fromrel=true : oauth2
- https://dzone.com/articles/oauth-20-vs-session-management?fromrel=true : oauth2

- https://oauth.net/videos/
- https://developer.okta.com/
- https://openid.net/
- https://oauth.net/2/
- https://www.udemy.com/course/oauth-2-simplified/?referralCode=B04F59AED67B8DA74FA7
- https://oauth2simplified.com/
- https://oauth.net/2/grant-types/implicit/


### HTTP

- https://app.pluralsight.com/library/courses/xhttp-fund/table-of-contents

#### Methods

An **idempotent** HTTP method is a HTTP method that can be called many times without different outcomes. It would not matter if the method is called only once, or ten times over. The result should be the same. 


**POST**

The HTTP POST method sends data to the server. The type of the body of the request is indicated by the Content-Type header.

The difference between PUT and POST is that PUT is idempotent: calling it once or several times successively has the same effect (that is no side effect), where successive identical POST may have additional effects, like passing an order several times.

**PUT**

The HTTP PUT request method creates a new resource or replaces a representation of the target resource with the request payload.

The difference between PUT and POST is that **PUT is idempotent**: calling it once or several times successively has the same effect (that is no side effect), where successive identical POST may have additional effects, like passing an order several times.

Request has body :	Yes
Successful response has body "	No
Safe "	No
Idempotent :	Yes
Cacheable :	No
Allowed in HTML forms :	No

**PATCH**  
The HTTP PATCH request method applies partial modifications to a resource.
The HTTP PUT method only allows complete replacement of a document. Unlike PUT, PATCH is not idempotent, meaning successive identical patch requests may have different effects. 

Request has body :	Yes
Successful response has body :	Yes
Safe :	No
Idempotent : No
Cacheable :	No
Allowed in HTML forms :	No

https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH

#### REST

- https://app.pluralsight.com/library/courses/designing-restful-web-apis/table-of-contents : Designing RESTful Web APIs

**Richardson Maturity Model**
Level 0 - The swarm of POX : using HTTP as a transport system for remote interactions
Level 1 - Resources  
Level 2 - HTTP Verbs   
Level 3 - Hypermedia Controls  

![Rchardson Maturity Model](https://github.com/himkak/notes/blob/master/SystemDesign/Http_RichardsonMaturityModel.png)

- https://martinfowler.com/articles/richardsonMaturityModel.html

- https://restfulapi.net/resource-naming/

- https://pages.apigee.com/rs/351-WXY-166/images/Web-design-the-missing-link-ebook-2016-11.pdf

##### Rest Best practises

- Use nouns to represent resources
- Use forward slash (/) to indicate hierarchical relationships
- Do not use trailing forward slash (/) in URIs
- Use hyphens (-) to improve the readability of URIs
- Do not use underscores ( _ )
- Use lowercase letters in URIs
- Never use CRUD function names in URIs
- Use query component to filter URI collection
- resources archetype can be divided into 4 types :
	document : 
			A document resource is a singular concept that is akin to an object instance or database record
			Use “singular” name to denote document resource archetype.

				http://api.example.com/device-management/managed-devices/{device-id}
				http://api.example.com/user-management/users/{id}
				http://api.example.com/user-management/users/admin
	collection :
			A collection resource is a server-managed directory of resources.
			Use “plural” name to denote collection resource archetype.

			http://api.example.com/device-management/managed-devices
			http://api.example.com/user-management/users
			http://api.example.com/user-management/users/{id}/accounts
	store :
			A store is a client-managed resource repository. A store resource lets an API client put resources in, get them back out, and decide when to delete them
			Use “plural” name to denote store resource archetype.

			http://api.example.com/song-management/users/{id}/playlists
	controller :
			A controller resource models a procedural concept. Controller resources are like executable functions, with parameters and return values; inputs and outputs.
			Use “verb” to denote controller archetype.

			http://api.example.com/cart-management/users/{id}/cart/checkout
			http://api.example.com/song-management/users/{id}/playlist/play



### GRPC

- https://www.youtube.com/watch?v=X9N2MP7D6i0

### AVRO RPC

### TCP

### UDP

### WebSockets

- https://www.youtube.com/watch?v=i5OVcTdt_OU : What are WebSockets | How is it different from HTTP?


</details>


## Capacity planning
- https://blog.newrelic.com/engineering/capacity-planning/
- https://wso2.com/whitepapers/capacity-planning-for-application-design-part-1/




<details>
<summary> Generic Approach to solve system design questions
</summary>

## How to approach a problem

1. **Requirement Gathering**	:
	- Define the scope of the problem
	- Clarify and agree on the scope of the system
	- User cases (description of sequences of events that, taken together, lead to a system doing something useful)
		- Who is going to use it?
		- How are they going to use it?
	- Constraints
		- Mainly identify traffic and data handling constraints at scale.
		- Scale of the system such as requests per second, requests types, data written per second, data read per second)
		- Special system requirements such as multi-threading, read or write oriented.

2. **Identify the high level components**
	- Define their domain


2. **System interface definition** : Identify the APIs to be exposed		


3. **Back-of-the-envelope capacity estimation** : 		
		estimate the scale of the system you’re going to design.		
		How much storage would we need?		
		What network bandwidth usage are we expecting?		
		
		
4. **Defining the data model**
		Which database system should we use? Would NoSQL like Cassandra best fits our needs, or we should use MySQL-like solution.
		
5.	**Identify the data storage system**:  
		Points to be considered :  
			- If the data is for premanemnt storage or temporary ? If temporary then we can prefer any cache.  
			- If cache, what will be the eviction policy ?  
			- What data structure required to store the data ?  
			- What all operations will be performed on the data ?  
			- Amount of data  
			- Will data increase in future ? Is horizontal scalability required for the data to store ?  
			- What is the TPS to support  
			- How much latency is allowed  
			- Will reads be consistent or eventual consistent  
			- Availability ? is 100% availability of data required ?  
						
						
6. **High-level design**  
		Draw a block diagram with 5–6 boxes representing core components of your system. You should identify enough components that are needed to solve the actual problem from end-to-end.
7. **Detailed design for selected components**  
		- If we’ll be storing a huge amount of data, how should we partition our data to distribute it to multiple databases?  
		- How much and at which layer should we introduce cache to speed things up?  
		- What components need better load balancing?  
8. **Identifying and resolving bottlenecks**  
		- Is there any single point of failure in our system? What are we doing to mitigate it?  
		- Do we’ve enough replicas of the data so that if we lose a few servers, we can still serve our users?  
		- Similarly, do we’ve enough copies of different services running, such that a few failures will not cause total system shutdown?  
		- How are we monitoring the performance of our service? Do we get alerts whenever critical components fail or their performance degrades?  
		
### Points to take care while designing a distributed system
- fault tolerant

</details>

<details>
<summary> Deployment Management
</summary>

### Docker

### Kubernetes

### Jenkins

### AWS Lambda

### Canary Deployment

- https://www.youtube.com/watch?v=3IJ5ko8jSIA&list=WL&index=90

### Blue Green Deployment

### AB Testing

- https://www.youtube.com/watch?v=zFMgpxG-chM



</details>

<details>
<summary> Examples
</summary>


### design a short URL system 

- https://github.com/himkak/notes/blob/master/SystemDesign/tinyUrl.md

### Designing Typeahead Suggestion



### design chrome autocompletion

### Chat Applications 

- https://github.com/himkak/notes/blob/master/SystemDesign/WhatsApp.md

### Notification
- GCM (Google Cloud Messaging) server is used to send notification to apps
- XMPP protocol is used

### Video Streaming

#### Netflix

- https://github.com/himkak/notes/blob/master/SystemDesign/netflix.md

- https://www.geeksforgeeks.org/system-design-netflix-a-complete-architecture/

#### youtube

- http://blog.gainlo.co/index.php/2016/10/22/design-youtube-part/

- http://blog.gainlo.co/index.php/2016/11/04/design-youtube-part-ii/


### Ride Sharing like Uber

- https://www.youtube.com/watch?v=NOHQ15lwHKY : Uber System Design | Design Ride-Hailing Application | System Design Interview



### Social Media

#### facebook

- http://highscalability.com/blog/category/facebook

- http://highscalability.com/blog/2015/11/14/how-facebooks-safety-check-works.html

- http://highscalability.com/blog/2010/8/2/7-scaling-strategies-facebook-used-to-grow-to-500-million-us.html

#### Twitter


https://github.com/himkak/notes/blob/master/SystemDesign/twitter%20timeline/Twitter.md
 

#### Instagram

- https://www.youtube.com/watch?v=da7mdMz0g0g : Instagram System Design | Design Photo-Sharing Application | System Design Interview
- https://techtakshila.com/system-design-interview/chapter-1
- https://www.youtube.com/watch?v=hnpzNAPiC0E


- 400M users
- 4+ B likes
- 100M photos/videos upload
- Top account: 110M followers

### Ticket booking system

#### Expedia

#### MakeMyTrip

### TIme Series

#### FitBit

### E-Commerce

- http://blog.gainlo.co/index.php/2016/08/22/design-ecommerce-website-part/

- http://blog.gainlo.co/index.php/2016/08/28/design-ecommerce-website-part-ii/

#### Amazon

- http://highscalability.com/amazon-architecture





### Distributed cache

- https://www.youtube.com/watch?v=U3RkDLtS7uY

### Web Crawler

- https://github.com/donnemartin/system-design-primer/tree/master/solutions/system_design/web_crawler
- http://blog.gainlo.co/index.php/2016/06/29/build-web-crawler/
- http://blog.gainlo.co/index.php/2016/06/29/build-web-crawler/
- http://infolab.stanford.edu/~olston/publications/crawling_survey.pdf
- https://medium.com/@morefree7/design-a-distributed-web-crawler-f67a8ebb8336

- https://github.com/himkak/library/blob/master/system%20design/GrokkingTheSystemDesign_Educative_Designing%20a%20Web%20Crawler.pdf
- https://www.youtube.com/watch?v=BKZxZwUgL3Y
- https://medium.com/@morefree7/design-a-distributed-web-crawler-f67a8ebb8336

### Search Engine

#### Google

- http://highscalability.com/google-architecture

- https://www.youtube.com/watch?v=KyCYyoGusqs


### key value store

- http://blog.gainlo.co/index.php/2016/06/14/design-a-key-value-store-part-i/
- http://blog.gainlo.co/index.php/2016/06/21/design-key-value-store-part-ii/

### Garbage collection system

- http://blog.gainlo.co/index.php/2016/07/25/design-a-garbage-collection-system-part-i/

- http://blog.gainlo.co/index.php/2016/08/08/design-garbage-collection-system-part-ii/

### Dropbox

- http://blog.gainlo.co/index.php/2016/09/12/dropbox-interview-design-hit-counter/

### Rate limiting

- https://www.ably.io/blog/distributed-rate-limiting-scale-your-platform/
	
	
### Auto Suggest System

- use trie data structure. Every suggestion node will also have score and we will show the result sorted.
- To improvize it, save the suggestions in each node
- To improvize more create a hashMap, with prefix <-> suggestions
- https://www.youtube.com/watch?v=xrYTjaK5QVM

</details>




<details>
<summary> References
</summary>



## References:


- https://drive.google.com/drive/folders/1OOM9DvWK3uWrlC-itxycbYroDS439Fhv : system design from algo-expert...
- https://drive.google.com/drive/u/0/folders/1nDXkIzCQ1KQ2DnovRqSkMOTwmLzXA5iX : system design foundation...

- https://github.com/donnemartin/system-design-primer/tree/master/solutions/object_oriented_design : sample oops problem

- https://github.com/donnemartin/system-design-primer/tree/master/solutions/system_design : sample system design problems

- https://www.pramp.com/ : practise system design questions with mock interview

- https://hackernoon.com/anatomy-of-a-system-design-interview-4cb57d75a53f  : high level steps to approach a problem   

- https://coursehunters.online/t/systems-design-fundamentals-glossary/2977 : Contains the glossary of the keywords used by architects    

- https://www.youtube.com/channel/UCn1XnDWhsLS5URXTi5wtFTA?view_as=subscriber : vidoes on designing system   

- https://github.com/binhnguyennus/awesome-scalability

- https://techtakshila.com/system-design/chapter-1



- https://medium.com/javarevisited/top-5-courses-to-learn-software-architecture-in-2020-best-of-lot-5d34ebc52e9



- https://www.coursera.org/learn/software-architecture?ranMID=40328&ranEAID=JVFxdTr9V80&ranSiteID=JVFxdTr9V80-w0sDNc1Z52m5QrxY66y1jg&siteID=JVFxdTr9V80-w0sDNc1Z52m5QrxY66y1jg&utm_content=10&utm_medium=partners&utm_source=linkshare&utm_campaign=JVFxdTr9V80 : Software Architecture

- https://app.pluralsight.com/library/courses/developer-to-architect/table-of-contents?aid=7010a000001xAKZAA2 : Developer to Architect

- https://www.developertoarchitect.com/ : developer to architect

- https://app.pluralsight.com/library/courses/clean-architecture-patterns-practices-principles/table-of-contents?aid=7010a000001xAKZAA2 : Clean Architecture: Patterns, Practices, and Principles

- https://www.quora.com/q/naiehxlhbpjhhons?q=system%20design

- http://highscalability.com/all-time-favorites/

### TODO

- https://medium.com/javarevisited/25-software-design-interview-questions-to-crack-any-programming-and-technical-interviews-4b8237942db0

- https://www.udemy.com/course/preparing-for-system-design-interviews/?ranMID=39197&ranEAID=JVFxdTr9V80&ranSiteID=JVFxdTr9V80-tonMQGx01Um4VXRheXg41A&LSNPUBID=JVFxdTr9V80&utm_source=aff-campaign&utm_medium=udemyads

- https://learning.oreilly.com/videos/software-architecture-fundamentals/9781491901144

- https://www.coursera.org/specializations/software-design-architecture

- https://gist.github.com/vasanthk/485d1c25737e8e72759f : System Design Cheatsheet

- https://github.com/himkak/library/tree/master/system%20design : Grokking the system design

- https://hackernoon.com/10-tips-for-using-diagrams-to-ace-the-system-design-interview-906p3609 

- How to reach the numbers for NFRs

- https://www.notion.so/73e875fdfffd48f588d9e643afb16275?v=0c0dd4236ad3474daa9e905b025618a0 : Yogesh Notes

#### GCP

- https://learning.oreilly.com/videos/gcp-complete-google/9781788999519
- https://app.pluralsight.com/library/courses/google-cloud-platform-fundamentals/table-of-contents

#### Azure

- https://info.microsoft.com/ww-thankyou-azure-infra-introduction-to-iaas-on-demand-webinar.html?LCID=en-in&ocid=mkto_eml_em593935a1la1&ocid=eml_pg163405_gdc_comm_az

- https://docs.microsoft.com/en-gb/learn/modules/intro-to-azure-fundamentals/

- 
#### AWS



### Google System Design Interview Prep Refs

- https://www.youtube.com/watch?v=Gg318hR5JY0 : Prepare for Your Google Interview: Systems Design


### Big organizations Engineering blogs

- https://dev.to/seattledataguy/11-of-the-best-engineering-blogs-2aah : 11 Of The Best Engineering Blogs To Inspire You

- https://developers.facebook.com/videos/


### Grokking the system design course

- https://coursehunters.online/t/educative-io-design-gurus-grokking-the-system-design-interview-part-1/579
- https://coursehunters.online/t/educative-io-design-gurus-grokking-the-system-design-interview-part-2/580
- https://coursehunters.online/t/educative-io-design-gurus-grokking-the-system-design-interview-part-3/581
- https://coursehunters.online/t/educative-io-design-gurus-grokking-the-system-design-interview-part-4/583
- https://coursehunters.online/t/educative-io-design-gurus-grokking-the-system-design-interview-part-5/584


### Overview of Realtime Streaming Protocols
- https://assets.ctfassets.net/3prze68gbwl1/5fKNVB8OWEC1pr7h96jnO3/d1ee79e160398554893158370269839c/overview-of-realtime-streaming-protocols.pdf

### GCP course in coursera

-  https://www.coursera.org/specializations/gcp-architecture?ranMID=40328&ranEAID=vedj0cWlu2Y&ranSiteID=vedj0cWlu2Y-8q8Xs1UPwqz6Z6XXL6MH1w&siteID=vedj0cWlu2Y-8q8Xs1UPwqz6Z6XXL6MH1w&utm_content=10&utm_medium=partners&utm_source=linkshare&utm_campaign=vedj0cWlu2Y


### Events Microservices kafka confluent

- https://event.on24.com/eventRegistration/console/EventConsoleApollo.jsp?simulive=y&eventid=2515222&sessionid=1&username=&partnerref=&format=fhaudio&mobile=&flashsupportedmobiledevice=&helpcenter=&key=AC93D048AB08844F9A1CC4CD4CC7595C&newConsole=true&nxChe=true&newTabCon=true&text_language_id=en&playerwidth=748&playerheight=526&eventuserid=416809601&contenttype=A&mediametricsessionid=359075447&mediametricid=3542501&usercd=416809601&mode=launch

- https://event.on24.com/eventRegistration/console/EventConsoleApollo.jsp?simulive=y&eventid=2515400&sessionid=1&username=&partnerref=&format=fhaudio&mobile=&flashsupportedmobiledevice=&helpcenter=&key=C8239323D1AA9F2176B42FB2A7C0BA00&newConsole=true&nxChe=true&newTabCon=true&text_language_id=en&playerwidth=748&playerheight=526&eventuserid=416809608&contenttype=A&mediametricsessionid=359075810&mediametricid=3542756&usercd=416809608&mode=launch

- https://event.on24.com/eventRegistration/console/EventConsoleApollo.jsp?simulive=y&eventid=2515418&sessionid=1&username=&partnerref=&format=fhaudio&mobile=&flashsupportedmobiledevice=&helpcenter=&key=F9BFB60CA2B02E9F9A8B4037A2FA0445&newConsole=true&nxChe=true&newTabCon=true&text_language_id=en&playerwidth=748&playerheight=526&eventuserid=416809612&contenttype=A&mediametricsessionid=359075945&mediametricid=3542780&usercd=416809612&mode=launch

# Generic Requirements

## Comparison of databases, which to use when

## Event Streaming

## CQRS

## Upload file/photos/videos

### Dropbox

### Google Drive

## Manage Post with comments & likes as Insta/ FB/ twitter has

## Login functionality authentication & authrization

## ecommerce 

## ticket booking like book my show

## Distributed Counter

## Rate limiter

## Web Crawler

## Video Streaming Netflix/youtube/tiktok

## Notification

## Chat app whatsapp/slack/discord

## Distributed cache

## Type Ahead

</details>
