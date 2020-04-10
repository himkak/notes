# NOSQL
## what is mongodb 
### advantages of mongodb
- schemaless
- mongod, mongo shell
- mongodb sub document cant be larger than 16mb size
- javascript is the interaction language in mongo shell
- mongodb has pluggable storage engine

## commands: CRUD
	help
	db : prints the name of the current db being used
	use <db>
	
### CREATE:
	When you insert somethiing into a collection the collection is made by itself if its not present. When a document is inserted if the inserted document doesnt have _id field, mongodb inserts that by itself. _id is kind of primary key. It can have complex values too
	db.<collection>.save({...})
	db.<collection>.insert({...})
	  If _id is not provided in the input json while inserting the document, mongodb creates a _id field , its value being unique objectid, and the document is inserted along with this objectId
	  
### READ:
	`db.<collection>.find()` : COmbine it with pretty to print the output in a better way. To get all the documents
	`db.<collection>.find({...})`
	`db.<collection>.findOne()`
	`db.<collection>.findOne({...})`
	  Findone gets back one document at random
	  The first argument of find/findOne is the where clause, the second optional argument is the projection clause, that is what fields needs to be shown in the output response. _id by default is set to true, and rest of fields are set to false by default.
	`db.students.find({students:19, type:"essay"})` : This is combination of 2 conditions, join them with and. Means find document where student is 19 and type is essay
	
	using comparison operators like : $gt, $lt, $gte, $lte, $ne, $elemMatch etc
	db.students.find({score:{$gt:90}}): using comparison operator $gt
	db.students.find({score:{$gt:90, $lt:100}})
	
	The comparisons dont span data types, means if while comparison we use string then field with numeric value will not be returned.
	
	`db.people.find({profession:{$exists:true}})` : to find documents having profession field
	
	`db.people.find({profession:{$type:2}})` : where the value type of the field is string
	
	`db.people.find({profession:{$regex:"a"}})` : to compare the value with regex, regex operator is slow, and not efficient
	
	`db.scores.find({$or:[{score:{$lt:50}},{score:{$gt:90}}]})` : using or operator to find score less than 50 or greater than 90.
	
	`db.scores.find({$and:[{score:{$gt:50}},{score:{$lt:90}}]})`
	
	quering for sub documents of type array: 
	favs collection: 
		{name:"him",favourites:["beer", "study"]}
		{name:"ram",favourites:["ice cream", "study"]}
		{name:"sam",favourites:["saavdhan", "play"]}
		{name:"ghai",favourites:["water", "study"]}
	To find favouries with value study: db.favs.find({favouries:"study"}) returns {name:"him",favourites:["ice cream", "study"]}, {name:"him",favourites:["beer", "study"]}, {name:"ghai",favourites:["water", "study"]}
	
	To match multiple values in array :
	db.favs.find({favouries:{$all:["study","beer"]}}) will return {name:"him",favourites:["beer", "study"]}
	
	To match values in array with or means where fav is either study or beer
	db.favs.find({favouries:{$in:["study","beer"]}}) will return {name:"him",favourites:["beer", "study"]}, {name:"ram",favourites:["ice cream", "study"]}, {name:"ghai",favourites:["water", "study"]}
	
	To compare inside nested document:
	Eg: users db:{name:"richard", email:{work:"r@work.com", personal:"r@home.com"}}
	to find with work email : db.users.find({"email.work":"r@work.com"})
	Eg:catalog db:{product:"Soap", price:10000, reviews:[{user:"fred", comment:"great", rating:4},{user:"him", comment:"great", rating:5}....]}
	price gretaer than 100 & rating greater than 4: db.catalog.find({price:{$gt:100}, reviews.rating:{$gt:4}})
	
	sort
	
	limit 
	
	skip
	
	order: sort, skip, limit
	
	count:
	db.<collection>.find({...}).count() 
	db.<collection>.count({...}).
	
	
	
	
### UPDATE:
		To update a whole document:
		`db.people.update({name:"Smith"},{name:"Thomson",salary:10000})` : this will update the document replcaing the old fields with the new one, the objectId will remain the same.
		
		TO update a specific field of a document, and if not present add it
		use $set: `db.people.update({name:"Smith"},{$set:{age:30}})`
		
		TO increment a specific field, if the field is present increment it and if not present add that field and set its value to inc value
		use $inc: `db.people.update({name:"Smith"},{$set:{age:30}})`  : increments age by 1 
		
		To remove a specific field from a document
		$unset: `db.people.update({name:"Smith"},{$unset:{age:1}})` : This will remove the age field from the document
		
		TO modify specific element in an array:
		`db.arrays.update({_id:0},{$set:{"a.2":5}})` : This updates the 3rd element of the array a and sets it to 5
		
		To add an element into an array into the right side of array:
		`db.arrays.update({_id:0},{$push:{a:6}})`
		
		TO remove the right most element from array use $pop
		`db.arrays.update({_id:0},{$pop:{a:1}})`
		
		TO remove the left most element from array use $pop
		`db.arrays.update({_id:0},{$pop:{a:-1}})`
		
		TO add multiple elements into array use pushAll
		`db.arrays.update({_id:0},{$pushAll:{a:[9,10]}})`
		
		To remove a specific element from an array
		`db.arrays.update({_id:0},{$pull:{a:9}})`
		
		pullAll
		
		TO add element to a  set if element is not present use addToSet, if present dont add
		`db.arrays.update({_id:0},{$addToSet:{a:8}})`
		
### UPSERT:
       To update document if present, if not present insert a new document.
	   `db.people.update({name:"Geo"},{$set:{age:40}},{upsert:true})`
	   
	   To update multiple documents:
	   `db.people.update({name:"Geo"},{$set:{age:40}},{multi:true})`
	   
### REMOVE:
	  `db.people.remove({})` : removes all documents from people collection
	  `db.people.remove({<where clause>})`
	  
	  `db.people.drop()` : dorps the collection
	  
	  `db.<collection>.deleteOne(...)`
	  `db.<collection>.deleteMany(...)`
	  
	  
### AGGREGATE:



   group: arregate stage, use sum, count
   Aggregation functions that can be used with group: 
	   $sum
	   $avg
	   $min
	   $max
	   $push, $addToSet : to push elements into the resulting array
	   $first, $last: mainly used after sorting the documents
   
	  To find the number of products by each manufacturer : So first we do group on manufacturer and then keep on adding 1 on finding a new product
	  db.products.aggregate([ {$group: { _id:"$manufacturer", num_products:{$sum:1}  } } ])
	  
	  To find number of products by each manufacturer and in each category: use group and  the id will have complex value 
	  db.products.aggregate([ {$group:  { _id:{manufacturer:"$manufacturer", category:"$category"},	num_products:{$sum:1} } } ])
	  
	  To find the sum of price of products by each manufacturer: group by manufacturer, sum the prices
	  db.products.aggregate([ {$group: { _id:"$manufacturer", sum_prices:{$sum:"$price"}  } } ])
	  
	  TO find the average price by category:
	  db.products.aggregate([{$group:{_id:"$category", avg_price:{$avg:"$price"}}}])
	  
	  To find out what products each manufacturer sells:
	  db.products.aggregate([{$group:{_id:"$manufacturer", products:{$addToSet:"$product_name"}}}])
	  
	  
	  
	  project: to reshape the documents: remove keys, add new keys, reshape keys, use some simple functions on keys: toUpper, toLower, add, multiply
	  db.products.aggregate([{$project:{_id:0,"maker":{$toLower:"$manufacturer"}, details:{category:"$category", price:{$multiply:["$price",10]}, item:"$name"}}}])
	  
	  
	  match: filter step
	  db.zips.aggregate([{$match:{state:"CA"}}])
	  db.zips.aggregate([{$match:{state:"CA"}},{$group:{_id:"$city", population:{$sum:"$pop"}, zip_codes:{$addToSet:"$_id"}}}])
	  db.zips.aggregate([{$match:{state:"CA"}},{$group:{_id:"$city", population:{$sum:"$pop"}, zip_codes:{$addToSet:"$_id"}}},{$project:{_id:0,city:"$_id",population:1}}])
	  
	  
	  sort: 
	  sorting can be done disk based and memory based. Memory based sorting can use max of 100mb space
	  db.zips.aggregate([{$match:{state:"CA"}},{$sort:{population:-1}}])

	  
	  skip:
	  preferred to be used after sort
	  db.zips.aggregate([{$match:{state:"CA"}},{$sort:{population:-1}},{$skip:10}])
	  
	  
	  limit
	  preferred to be used after skip
	  db.zips.aggregate([{$match:{state:"CA"}},{$sort:{population:-1}},{$skip:10},{$limit:5}])
	  
	  unwind: to open the arrays, and seperate them into diff documents
	  db.zips.aggregate([{$unwind:"$tags"}])
	  
	  redact: security related, documents that specific users see
	  
	  geonear: perform location based queries
	  
	  
### Mongo Import: 
      mongoimport --db users --collection contacts --file contacts.json

### Mongod:
	  to start the mongod server.
	  -dbpath
	  -port
	  -storageEngine
	  
## Storage Engine:
	 ### MMAP:###
	 provides collection level locking, in place update, documents are provided space in power of 2,
	 ###Wired Tiger:###
	 -document level concurrency. It is lock free implementation using optimistic locking mechanism.
	 -offers compression both of data and of indexes.
	 -no in place update,
	 
## INDEXES:
	 If we have indexes on a,b,c searching can be done on a or a,b or a,b,c and not on b or c or b,c
	 Indexing slows down the writes, but fasten up the reads. SO good practise is to add all data in the collection and after data is added then add the indexes
	 db.studenst.createIndex({studentId:1}) : create index on studentId ascending
	 db.studenst.createIndex({studentId:1, classId:-1}): creates a compound index on studentId ascending and classId descending
	 db.studenst.getIndexes() : to get all the created indexes
	 There is always an index on _id field by default
	 db.studenst.dropIndex({studentId:1}) : to delete a index
	 
	 Indexes on arrays
	 compound indexes on 2 arrays fields is not allowed in mongodb
	 
	 To create index on sub-element use . notation
	 db.studenst.createIndex({"student.score":1})
	 
	 unique index:
	 IN case of unique index, no 2 documents can have same field value for the unique indexed field
	 db.studenst.createIndex({studentId:1}, {unique:true})
	 
	 sparse index:
	 When index key is missing from some of the documents. 
	 For this kind of keys we can set the sparse option, that tells db server that it will not include the documents that are missing the key
	 db.studenst.createIndex({cellPhone:1}, {unique:true,sparse:true})
	 
	 Index creation in foreground or background
	 foreground indexing:by default, fast, it blocks all the readers and writers to the db
	 background indexing:to be asked for,slow, dont block readers and writers : db.studenst.createIndex({cellPhone:1},{background:true})
	 
	 Index size:
	 db.students.stats(): In its response, we will find index size field
	 
	 In wired tiger indexes take less space as compared to MMAP storage engine
	 
	 We can suggest mongodb to use which index and that is done by hint function.
	 
	 Efficient index: look at the find query, and identify the element which can reject max number of docs from the input.
	 Eg: db.students.find({student_id:{$gt:500000}, class_id:54}).sort({final_grade:-1})
	 So in this query the index on class_id will reject max number of docs from the input. next element in the search is student_id. next we have to sort the result using final_grade.
	 So a compound index is made
	 Final index: {class_id:1, final_grade:1, student_id:1}
	 
### EXPLAIN: 
	to see what the db does with query
     db.students.explain().find({studentId:5}): this doesnt runs the query
	 The winningPlan section tells us if index were used to execute this query. winningPlan has indexName 
	 db.students.explain(true).find({studentId:5}): this runs the query, and we can get more info in executionStats section like no of docs examined, execution time
	 
	 Differenet modes of explain command:
	 queryPlanner: default mode: it tells us about the winning plan, the rejected plan
	 executionStats: includes the queryPlanner mode : db.students.explain("executionStats").find({studentId:5}), tells us about the execution statistics for the winning plan: execution time, total docs examined, number of documents returned, information about each stage
	 allPlansExecution: includes the executionStats mode
	 
COVERED QUERY: It is the one that is fully satisfied by index and 0 docs needs to be inspected. This can be verified by seeing the explain --> executionStats result, and in that totalDocsExamined should be 0


Java Mongo Driver API:
	Sample code:
	
	    MongoClient mongoClient = new MongoClient(new MongoClientURI("mongodb://localhost"));
        MongoDatabase blogDatabase = mongoClient.getDatabase("imagescoll");
        MongoCollection<Document> imagesCollection=blogDatabase.getCollection("images");
		imagesCollection.find();
		
		
Write concerns: Write concern describes the level of acknowledgement requested from MongoDB for write operations to a server
	   w:1 = wait for update to be written to disk
	   j:false = dont wait for update to be written to journal. If data not written 
	   
	   w:j
	   1:false : default, wait for write to be ack by db but dont wait for journal to written to db, this is fast, but there is small window of vulnarability
	   1:true : wait for write to be ack by db and wait for journal to written to db, slow, but no window of vulnarability
	   0	  : write will not wait for ack, app will just send the write and proceed and it will not w8 for ack
	   
	   
REPLICATION:
	  Replica set: set of replicas, consists of primary and secondaries, generally 1 primary and 2 secondaries. App writes to the primary and data is copied from primary to secondaries.
	  If primary goes down , there is election between 2 secondaries that which will become primary. Majority of nodes are reqd to be presnet in election to select the primary.
	  
	  Types of replica set nodes:
	  regular : can vote
	  arbiter : only for voting purpose, doesnt backsup data. very useful
	  delayed : is some hrs dalayed, that means copies data some hrs later. can vote, cant become primary
	  hidden  : cant become primary, can vote
	  
	  Writes always goes to primary
	  Reads can go to primary and secondary depending on read preference.
	  
	  During failover period writes cant complete, because there is time period which is reqd for primary to be elected.
	  
	  command to create replica set:
	  mongod --replSet rs1 --logpath "1.log" --dbpath /data/rs1 --port 27017 --fork
	  mongod --replSet rs1 --logpath "2.log" --dbpath /data/rs2 --port 27018 --fork
	  mongod --replSet rs1 --logpath "3.log" --dbpath /data/rs3 --port 27019 --fork
	  fork: tells terminal cursor to return 
	  After this they need to be initiated with config
	   config={_id:"rs1",members:[{_id:0, host:"localhost:27017", priority:0, slaveDelay:5}, {_id:1, host:"localhost:27018"}, {_id:2, host:"localhost:27019"}]}
	   rs.initaiate(config)
	   rs.status()
	  To be initiated from host which can become primary. In the above config cant execute in 27017
	  cant write on secondary, cant query secondary by default. So use rs.slaveOk() command and after this we can read from secondary.
	  
	  Every mongod server has oplog (operation log). When a opertaion is executed on primary, the oplog is updated with that info. The secondaies looks into primary's oplog and applies that operation on their side and updated the oplog. This oplog is present in local db ->oplog.rs collection. oplog is capped collection
	  
	  Failover and rollback: suppose some operation has been done on primary and that has been updated in oplog, but it has not yet been copied to secondary and the primary goes down. The secondary will become primary. This new primary will not have that operation that was not copied. Now that machine comes back up again as secondary and it has some operations in oplog that that are not present in new primary. So those operations will be rolled back and will be kept in a file. These operations if reqd will have to be manually applied.
	  
	  
### SHARDING: 
	 Horizontal scaling
	 Sharding is a type of database partitioning that separates very large databases the into smaller, faster, more easily managed parts called data shards. The word shard means a small part of a whole.
	 mongo has mongos server that comes between mongod shards and the application. data is distributed between multiple mongod servers or multiple replica sets.
	 shard_key: mongos server has information that which shardKey belongs to which shard server. when a query comes mongos checks the shard key in that query and then decides to which shard server to send the query to.
	 Build a shard env:
	  eg: 3 shards[s0,s1,s2], each with 3 replica nodes, 1 mongos router. app talks to mongos router. 3 config servers. these config servers contains the info about which shard key belongs to which shard.
	  The config server contains 2 types of shard info, range based or hash based.
	  Range based: eg: 0 - 100 belongs to one chunk and that chunk lives in shard s1
	  
	  mongod --replSet s0 --logpath "1.log" --dbpath /data/s0 --port 27017 --fork --shardsvr
	  mongod --replSet s0 --logpath "2.log" --dbpath /data/s1 --port 27018 --fork --shardsvr
	  mongod --replSet s0 --logpath "3.log" --dbpath /data/s2 --port 27019 --fork --shardsvr
	  
	  after this configure the replica set:
	  config={_id:"s0",members:[{_id:0, host:"localhost:27017"}, {_id:1, host:"localhost:27018"}, {_id:2, host:"localhost:27019"}]}
	  rs.initaiate(config)
	  
	  same way for s1 and s2 on diff ports
	  
	  Next comes the config server:
	  mongod --logpath "cfg-a.log" --dbpath /config-a --port 57017 --fork --configsvr 
	  mongod --logpath "cfg-b.log" --dbpath /config-b --port 57018 --fork --configsvr 
	  mongod --logpath "cfg-c.log" --dbpath /config-c --port 57019 --fork --configsvr 
	  
	  start the mongos server by providding the config server's details
	  mongos --logpath "mongo-1.log" --configdb localhost:57017, localhost:57018, localhost:57019 --fork
	  
	  add shards by connecting to mongos router and providing the details of primary server of each replica set:
	  db.adminCommand({addshard:"s0/"+"localhost:27017"});
	  db.adminCommand({addshard:"s1/"+"localhost:37017"});
	  db.adminCommand({addshard:"s2/"+"localhost:47017"});
	  enable sharding on db school
	  db.adminCommand({enableSharding:"school"})
	  do sharding on students collection , shard key is student_id
	  db.adminCommand({shardCollection:"school.students", key:{student_id:1}})
	  
	  sh.status(): provides info of sharded system
	  
	  If the query doesnt contains the shard key, then the mongos router sends the command to all the shards, like for db.collection.find({})
	  If the query is using shard key like: db.collection.find({student_id:1000}), this will go to only one shard
	  
	  Implication of sharding on development:
	    every doc includes the shard key
		shard key is immutable
		index hsould start with shard key
		if no shard key the scattered gathered
		
		
SECURITY:
	  args used: --auth, --keyFile, --ssl
	  
	  -authentication:
	  can be done via:
	  --user/pwd: start mongod with --auth argument. the detail of user/pwd is saved in admin db, <dbname>.system.users collection. 
	  TO create a user : db.createUser(	{user:"him",pwd:"him",roles:["readWriteAnyDatabase"]} )
	  To connect using mongo client: mongo localhost/admin -u him -p him 
	  Different roles: read, readWrite, dbAdmin, userAdmin, clusterAdmin, readAnyDatabase, readWriteAnyDatabase, dbAdminAnyDatabase, userAdminAnyDatabase.
	  
	  In a cluistered setup, --keyFile is used to authenticate communication between diff servers.
	  Using --keyFile doesn't encrypt your data, it just makes sure that the servers authenticate one another using the keyfile. However, if the key file were sent across the network unencrypted, they wouldn't be of much use!
	  
	  Types of users:
	  admin: can do administration, created in admin db, can access all dbs
	  regular: access a specific db, read/write or read-olny
	  
	  
	  --ssl 
	  
	  -access control / authorization
	  
	  -encryption
	  
	  -network setup
	  
	  
BACKUP:
	  -mongodump, mongorestore
	   while taking backup of cluster we have to stop the balancer so that migration of data between servers stops. This is done by command sh.stopBalancer(). Then backup config db. The backup all the shards.
	   
	  -filesystem snapshot
	  
	  
CAPPED COLLECTIONS: static sized collection. they dont grow in size. kind of a circular queue. If the space is full the old one is removed and new one is added.

TTL Collections: achieved by creating special index

GridFS: Grid file system. here we can store files.