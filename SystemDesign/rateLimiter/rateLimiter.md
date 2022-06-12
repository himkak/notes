# Rate Limiter

- https://www.youtube.com/watch?v=CRGPbCbRTHA : Rate Limiting with Redis

- https://www.youtube.com/watch?v=mhUQe4BKZXs : Rate Limiting system design | TOKEN BUCKET, Leaky Bucket, Sliding Logs

- https://konghq.com/blog/how-to-design-a-scalable-rate-limiting-algorithm/ : How to Design a Scalable Rate Limiting Algorithm
- https://www.youtube.com/watch?v=HnSb8DFU5UA




![image](https://user-images.githubusercontent.com/17414949/173226564-64a78f69-9ce1-47b9-86b0-1585cb5b75d5.png)

![image](https://user-images.githubusercontent.com/17414949/173226603-ff91969f-f48a-4cb4-8b21-c9c82383781d.png)

![image](https://user-images.githubusercontent.com/17414949/173226651-082bc27d-da78-4115-8239-729efb508a8b.png)

#### Algorithms

- **Token bucket** : 
	- Approach : use redis, have a key value for every user. key = user Id, value = {lastUpdated, availableTokens}. 
	- For every request, reduce the token and update the lastUpdated.
	- If the available tokens is 0 reject the request, else update.
	- Every time before update check the lastUpdated, if the lastUpdated is within the window, then reduce the available token, else fill the token and then reduce.
	- Eg : 5 req/min 
	- Req 1 : time :15:30:10, value in db : userId1 : {lastUpdated: 15:30:10, availableTokens : 4 }
	- Req 2 : time :15:30:20, value in db : userId1 : {lastUpdated: 15:30:20, availableTokens : 3 }
	- Req 3 : time :15:30:21, value in db : userId1 : {lastUpdated: 15:30:21, availableTokens : 2 }
	- Req 4 : time :15:30:22, value in db : userId1 : {lastUpdated: 15:30:22, availableTokens : 1 }
	- Req 5 : time :15:30:23, value in db : userId1 : {lastUpdated: 15:30:23, availableTokens : 0 }
	- Req 6 : time :15:30:30, reject the request and dont update the db. As the request came in same minute.
	- Req 7 : time :15:31:01, value in db : userId1 : {lastUpdated: 15:31:01, availableTokens : 4 } Refill the tokens.
	- problem : concurrency issue

![image](https://user-images.githubusercontent.com/17414949/173226480-265db179-7cb6-4d7a-ab95-b6b9de4c410e.png)


- **Leaky bucket** :
	- TO be used when we want to serve specific number of requests at any given point of time.
	- Approach : Have a queue, with fixed size. Whcih ever request came first will be served first. If the queue is full, the new requests coming will be discarded.
				 As soon as there is space in queue, the new requests will be accepted. Traffic is smoothened.
- **Fixed window counter** :
	- Approach : Again we use redis. The key is : userId_TimeInHrMin : user1_11:00, and value is counter, with a ttl of 60 secs.
	- Problem : the load is not being evenly distributed
	
- **Sliding logs**:
	- If the window doesnt starts at 00 secs, then this approach is useful.
	- Approach : We keep a sorted collection (sorted set of redis) of the time at which the requests are coming and remove the ones which are older than 1 min.
					Every time check the no of elements in the list, if its greater than the allowed rate reject the request.
	- Problem : lot of data being saved in memory

- **sliding window counter** :
	- Extension of sliding logs.
	- Approach : Here we keep a count of no of request in that sec. So advantage is that, suppose 2 requests come at same sec. So we will have 1 entry with counter 2. But the sliding log we would had 2 elemenets in the collection. We can use the hashTable datastructure of redis.

![image](https://user-images.githubusercontent.com/17414949/173226368-99be9e4e-7e2d-4675-a2d1-3f5866a44740.png)

![image](https://user-images.githubusercontent.com/17414949/173226418-21cb5ff0-617e-4269-926a-27a707d661f0.png)

	
#### Distributed

![Rate limiter system design sticky session](https://github.com/himkak/notes/blob/master/SystemDesign/rateLimiter/rateLimiter_Distributed_SickySession.JPG)

- Approaach 1 : sticky session
	- Issue is single point of failure

- Approach 2 : locks on DB
	- Issue with this approach is latency
	
#### Anti patterns
![image](https://user-images.githubusercontent.com/17414949/173226517-93ed2191-d603-4438-a878-1ab2b467d87e.png)

