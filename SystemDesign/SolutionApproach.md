# How to approach a System Design problem

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
