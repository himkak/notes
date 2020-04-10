# Cassandra

- NoSql DB
- No master slave
- No leader election
- Not a replacement of RDBMS, you will have to change the data model.
- Cassandra stores data in table model, difference from relational is, a table can be distributed in different nodes. So we store denormalized data in cassandra.
- Apache cassendra is written in java

![Hash Ring](https://github.com/himkak/my-notes/blob/master/DB/Cassandra_HashRing.PNG)

- In CAP theorem, cassandra adheres AP
- Cassandra has different configurations to provide different behaviours
	- Replication Factor (RF) : In how many nodes the data should be replicated. The data is replicated to other master nodes. RF is set on keyspace level
	- Consistency Leven (CL) : ALL/QUORUM/ONE : From how many nodes should it pull(read) or write the data. ALL is fully consitent, QUORUM is highly consistent...
		CL is set per query level
- Depending on the CL the replication can happen asynchronously. If CL set to 1 and RF to 2, the write to 2nd node will be asynchronous.

- keyspace is similar to schema

![Write Path](https://github.com/himkak/my-notes/blob/master/DB/Cassandra_WritePath.PNG)

![Read Path](https://github.com/himkak/my-notes/blob/master/DB/Cassandra_ReadPath.PNG)

- In read the latest time stamp always wins

- Download Cassandra : http://cassandra.apache.org/download/

## Steps to use 

- `bin/cassandra.bat` : to start the cassandra server
- `bin/cqlsh.bat` : to start the sql terminal
- `DESCRIBE KEYSPACES` : to see all the keyspaces
- `CREATE KEYSPACE test_keyspace WITH replication = {'class': 'SimpleStrategy', 'replication_factor': '1'}  AND durable_writes = true;` : To create keyspace
- `use test_keyspace` : to use the keyspace just like to use schema in mysql
- `CREATE TABLE employee_by_id ( id int PRIMARY KEY,  name text, position text)` : to create table
- `INSERT INTO test_keyspace.employee_by_id (id, name, position) VALUES (2, 'him', 'se');` : insert data into table
- `select * from employee_by_id;` : fetch data from table

- **partition key** is used to identify the location of the data entered, in which node will the data go and sit in the ring. Consistent hashing algo is used for this.

- **Clustering column** is used to maintain order of data. we can even order at runtime using order by.
- In the below examplen we are creating primary key with cluster keys, this helps to maintain order, and adding id helps to maintain uniqueness.
![Clustering Column](https://github.com/himkak/my-notes/blob/master/DB/Cassandra_ClusteringColumn.PNG)

- In the above image state is the partition key.

![Querying Clustering Column](https://github.com/himkak/my-notes/blob/master/DB/Cassandra_QueryingClusteringColumn.PNG)


![Changing Default Order](https://github.com/himkak/my-notes/blob/master/DB/Cassandra_ClusteringColumnChangingDefaultOrder.PNG)


## How to connect via client

- https://academy.datastax.com/resources/getting-started-apache-cassandra-and-java-part-i : java client


## Node
Every instance of cassandra is called a node.
- To check the status of a node `nodetool info`