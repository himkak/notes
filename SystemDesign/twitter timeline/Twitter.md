# Twitter System Design 

- Difficulty level : medium


## Requirement Gathering
	- Scope of the problem
		- user should be able to see home timeline view. It should contain most recent tweets by all the people it follows
		- user should be able to Post tweets
		- User should be able to follow another user
		- user should be able to see all its tweets on dashboard : user timeline
		- user should be able to search tweets


## NFR
	- High Availability
	- Fault Tolerant
	- latency
	- eventual consistency
	- Horizotally scalable
	
## Estimation
	Text Messages:
		- Daily active users : 300E6
		- write : 300E3
		- total active users :
		- read:write = 1000:1 = 600,000 : 600
		- how much data to be stored
			per tweet : 300 bytes
			per day data = total tweets per day * per tweet size = 300E3 * 300 = 9E7
			
			Data for 5 yrs = 9E7 * 400(no of days per yr) * 5(no of yrs) = 180E9 Bytes / E9 = 180 GB
	Video:
		1 video size : 1E6 b
		no of users upload (10% of write users)= 300E3/10 = 3E5
		total data per day = 3E5 * 1E6 * 400 * 5 = 60E13= 600E12= 600  TB
	Video URL
		per day : 200 B * 3E5 =  60E6 = 60 MB
		5 yrs = 60 MB * 400 * 5 = 120 GB	
	
	-------------------
	Redis
		- write : 300E3 
		- per tweet : 300 bytes
		- tweetId : 40 B * 300E3 * 1000 = 12E9 B = 12 GB (per day)
		- home time per user 12 GB per day : 12 GB * 
		
		home timeline : 300E6 * 800 (total tweets per user) * 40B (per tweet tweetId, userId) = 96E11 =~ 10 TB * 3(Nodes) = 30 TB
		tweet, tweetId = 300E3 * 300 = 9E7 B per day = 9E7 * 400 = 36E9 B per yr = 36GB per yr * 3 = 102 GB per yr
	
		
### Numbers as of 2011
- 155M tweets / day
- max : 7k tweets / sec

## Identify the high level components
	- tools : 
		DB, Cache
		Video/image storage : S3 + CDN
		Microservice
		Load balancer

## Use case

### Post a tweet :
- Follows a write based fanout approach
- Fanout takes all the tweets coming in and places them in redis cluster
- Fanout communicates with social graph service to get the list of followers of the user.
- Fanout iterates all the followers and places the tweet in their home timeline list in redis cluster
- Home timeline is limited to 800 tweets.
- Every redis node is scaled to 3 nodes
- If the follower is not an active user(didnt logged in from last 30 days), no need to update its timeline object.
- For non-active user home timeline is not cached, and if this user logs in his home timeline is made by querying the DB
- Complexity of O(n) where n being the number of people following you
- Fanout to be done for non-celebrity.  
		Data storage :
			Tweet : text, userId, time, location, image url, video url
			followers : userId, followingUserId (1,2 : 1,3) 
			user : userName, userId, age...
			columnar : user timeline : timeLineIds
		
			Rest url 
		save
		services : 1 microservice : save posts
			async : Kafka
			1) fetch followers
			2) paralelly append the tweet to all the followers objects
			3) update cache
			


![Tweet Flow](https://github.com/himkak/notes/blob/master/SystemDesign/twitter%20timeline/TweetFlow.jpg)
	
### upload image/video
		post
		S3
		service : upload service

### home timeline
	Follows a pull based mechanism, using Rest API call
	GET, paginated
	input : userId, pageNo
	output : list of tweers : tweets of users u r following
	cache : timeline object : key : <userId>:tweets, value : list of tweets
	
		


![HOme timeline Flow](https://github.com/himkak/notes/blob/master/SystemDesign/twitter%20timeline/ShowHomeTimeline.jpg)

		
### Search
	Search write happens in O(1)
	Search read happens in O(n)
		
	DB
	- scaling
	- eventual consistency




***********************ROUGE / IN PROGRESS***********************************************

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




## References

- https://www.infoq.com/presentations/Twitter-Timeline-Scalability/ : Timeline 
- https://www.youtube.com/watch?v=J5auCY4ajK8 same content by another person

- https://www.youtube.com/watch?v=wYk0xPP_P_8
- https://github.com/himkak/library/blob/master/system%20design/GrokkingTheSystemDesign_Educative_Designing%20Twitter.pdf
- http://highscalability.com/scaling-twitter-making-twitter-10000-percent-faster

- https://blog.twitter.com/engineering/en_us.html
