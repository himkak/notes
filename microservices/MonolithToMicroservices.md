# Monolith to microservies

##  Patterns
- Strangler Pattern
- Branch by abstraction

- https://www.youtube.com/watch?v=9I9GdSQ1bbM : GOTO 2019 • Monolith Decomposition Patterns • Sam Newman : overview of all patterns

### Strangler Pattern

- Currently our api is being consumed from the monolith, but the microservice is also present in prod, but not yet released

![Monolith to microservice strangler initial stage](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_Strangler.JPG)


- We first test the microservice and when we have the confidence, we redirect the path to use microservice

![Monolith to microservice strangler initial stage](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_Strangler2.JPG)

### Branch by abstraction

- Suppose u want to take out notification service
- Create an interface over it and provide all its functionalities via interface
![Monolith to microservice Branch By abdtraction](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_BranchByAbstraction.JPG)

- Create a separate notification service microservice
- Consume it from your monolith via a rest client
- This client implements the same interface
![Monolith to microservice Branch By abdtraction](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_BranchByAbstraction2.JPG)

- Finally switch over to use the client, by just changing the implementation of the interface. We can use here a feature flag.
![Monolith to microservice Branch By abdtraction](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_BranchByAbstraction3.JPG)

- Later on clean up the notification service from the monolith and remove the feature flag
![Monolith to microservice Branch By abdtraction](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_BranchByAbstraction4.JPG)

- In order to test and validate, We can even run both the flows together and compare them. We can compare the data and the time being taken. Our src of truth will be existing ond service.
![Monolith to microservice Branch By abdtraction](https://github.com/himkak/notes/blob/master/microservices/MonolithToMicroservice_BranchByAbstraction5.JPG)

# How to break monolith DataBase

## Approach 1

- The initial stateof the monolith application and the monolith database
![Current State of Monolith App and Monolith data](https://github.com/himkak/notes/blob/master/microservices/MonoToMicro_DbBreak_Approach1_1.JPG)

- We break the relationship
![Current State of Monolith App and Monolith data](https://github.com/himkak/notes/blob/master/microservices/MonoToMicro_DbBreak_Approach1_2.JPG)

- Now the join is done by fetching the catalogue data using http (rest) from catalog service
![Current State of Monolith App and Monolith data](https://github.com/himkak/notes/blob/master/microservices/MonoToMicro_DbBreak_Approach1_3.JPG)

- The issue resides that if someone deletes the data from catalog db. Earlienr when there was a monolith db, it was not possible, as we have a foreign key relationship.
- So DB was managing the delete.
![Current State of Monolith App and Monolith data](https://github.com/himkak/notes/blob/master/microservices/MonoToMicro_DbBreak_Approach1_4.JPG)
- But now its not the same case
- one option is to do cascade delete. Yuu generate an event when u delete the row in catalog db, all
- or we could have done a soft delete
- 

### Problems
- More network hops
- lost of data integrity


# Our journey from monolith to microservices
- used strangler pattern
- Identify the different domains
- Identify the different APIs for evry domain
- break the monolith to multiple modules
- For every domain created a microservice, each having its own repository
- Move the APIs to their domains [lift and shift]
- Monolith worked as orchestrator, with feature toggle, to switch between the new API and old API. This is a pass through service. This worked as backup in production
- Added blue green deployemnt 
- For session, first moved the session from monolith to redis using spring session. Then started using JWT. jwt contained iimutable data.


# References :



https://dzone.com/articles/monolith-to-microservices-with-the-strangler-patte : Strangler Pattern