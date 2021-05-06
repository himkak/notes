# Tiny URL

## Requirements
- generate short url
- give option to provide self short url
- url to be valid for specific duration

## Follow up questions
- What is the length of the short URL

## NFR
- Highly Available
- real time, minimum latency
- Shortened links should not be guessable (not predictable).


## Capacity Estimation

### Traffic estimation
- Read to write ratio : 100:1
- No of new URLs per month = No of writes per month : 500 Million 
- No of redirects = No of reads = 500M * 100 = 50 Billion

- No of new URL per sec= 500M/(30 * 24 * 60 * 60) = 200 URLs/sec
- No of reads = 100 * 200 = 2*10^4 URLs/sec

### Storage estimation	 
- **For 5 yrs**
- Total no of URLs = 500M * 12 * 5 = 30 Billion
- Size per url, this includes the main url, short url, date time of storage = 500 Bytes
- Total size of data = 30 billion * 500 Bytes = 15 TB

### BandWidth estimation

- **For write**
- url per sec * size of each url = 200 * 500 bytes = 100KB/sec

- **For read**
- url per sec * size of each url = 2*10^4 * 500 = 10 MB/sec

### Memory estimation for caching of frequently accessed URLs

- Assume 80-20 ratio, means 80% of users read 20% url
- (No of Reads per sec / 5) * (3600*24) * (size per url) = 170GB

# DB
- Which DB to use
	- compare relational with NoSql
		- Relational : ACID, cant scale horizotally
		- NoSql : scale horizotally

## Data Structure to be stored in DB
- URL Table : short url, main url
- Data needs to be consistent

Database needs to be NoSql DB : Cassandra


## Short URL Generation

- To generate short URLs, we do encoding of the URL using base62 encoder.

## Imp points
- encoding : Base 62 vs MD5 vs Base 10: Base 62 as its size is controllable and it has 62 chars (a-z, A-Z, 0-9) which gives a combination of 62^7 (if our random string size is 7)
Base 10 uses 0-9 chars. Base 62 has less chance of collision, in comparison to Base 10
- Where to store the data, in relational or nosql : for scalability nosql
- for scalability how to generate short urls : zoo keeper

- zookeeper : distributed co-ordination service 

- How to generate URL using Base62 encoding
- How to prevent the short url conflict
	- Every time we generate short url, we can check in the DB if the short url exists or not.
	- If its already present regenerate.
	- So this solution will be slow as we wil have to check DB every time.
	- We can use a counter, but it will not be scalable
	- We can given different ranges to every microservice, but ths solution is also not scalable.
	- SO we go for using zoo keeper. zookeeper will manage the counter and will give ranges to different instances of the microservice. So with this we can auto scale also.
- If we scale our app[holding the logic to encode and generate short URL], how to make sure short URLs dont conflict
- If same url is provided by multiple users how to manage it efficiently.

![TinyUrlSystemDesign](https://github.com/himkak/notes/blob/master/SystemDesign/tinyUrl/TinyUrlSystemDesign.jpg)


## References
- https://www.youtube.com/watch?v=JQDHz72OA3c

- https://www.educative.io/courses/grokking-the-system-design-interview/m2ygV4E81AR : Designing a URL Shortening service like TinyURL
- https://github.com/himkak/library/blob/master/system%20design/GrokkingTheSystemDesign_Educative_Designing%20a%20URL%20Shortening%20service%20like%20TinyURL.pdf

