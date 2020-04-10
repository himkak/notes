
# Events

- https://www.youtube.com/watch?v=kyNL7yCvQQc : GOTO 2019 • Not Just Events: Developing Asynchronous Microservices • Chris Richardson


# Distributed Transactions

https://developers.redhat.com/blog/2018/10/01/patterns-for-distributed-transactions-within-a-microservices-architecture/

https://www.youtube.com/watch?v=S4FnmSeRpAY

## saga 
- Overview : A pattern for managing distributed transactions
- problem  : Transaction model when transactaions span over multiple microservices
- solution : break the txn into multiple sub-txns

- https://chrisrichardson.net/post/microservices/2019/07/09/developing-sagas-part-1.html
- https://chrisrichardson.net/post/sagas/2019/08/04/developing-sagas-part-2.html
- https://chrisrichardson.net/post/sagas/2019/08/15/developing-sagas-part-3.html
- https://chrisrichardson.net/post/sagas/2019/12/12/developing-sagas-part-4.html

- https://microservices.io/patterns/data/saga.html
- https://www.youtube.com/watch?v=YPbGW3Fnmbc
- https://microservices.io/patterns/data/saga.html
- https://www.youtube.com/watch?v=WnZ7IcaN_JA&t=58s

### Choreography
- It uses Events
- Choreography - each local transaction publishes domain events that trigger local transactions in other services

![Choreography](https://github.com/himkak/my-notes/blob/master/microservices/Saga_Choreography.PNG)

### Orchestration
- Orchestration - an orchestrator (object) tells the participants what local transactions to execute

![Orchestration](https://github.com/himkak/my-notes/blob/master/microservices/Saga_Orchestration.PNG)

#### Implicit orchestrator

![Implicit vs Explicit](https://github.com/himkak/my-notes/blob/master/microservices/Saga_ImplicitVsExplicit.JPG)

![Implicit](https://github.com/himkak/my-notes/blob/master/microservices/Saga_Orchestrator_Implicit.JPG)

#### Explicit Orchestrator
**Preferred over implicit**
![Explicit](https://github.com/himkak/my-notes/blob/master/microservices/Saga_Orchestrator_Explicit.JPG)

### 2 phase commit
- used by traditional monolith applications

# CQRS
- Separate data models, one for query optimized and other for command optimized. There will be duplicated data in both the models.
- https://microservices.io/patterns/data/cqrs.html

# Service Mesh
- https://www.youtube.com/watch?v=QiXK0B9FhO0 : What is a service mesh?

- service discovery : Eureka
- Load balancing : ribbon
- canary / rolling deploy
- distributed tracing 
- security

- service mesh solves all these challenges
- Its motto is "Do not burden my code with all these infrastructure related decisions"


# Event sourcing
- https://microservices.io/patterns/data/event-sourcing.html
- https://martinfowler.com/eaaDev/EventSourcing.html
- https://eventuate.io/whyeventsourcing.html
- https://www.youtube.com/watch?v=rsSld8NycCU : Scaling Event Sourcing for Netflix Downloads


- **Problem** : We can query an application's state to find out the current state of the world, and this answers many questions. However there are times when we don't just want to see where we are, we also want to know how we got there.

- **Solution** : Instead of just storing the current state, we also store the events that leads to the current state.

- Event store : Databse optimized for storing events

![Advantages of event sourcing](https://github.com/himkak/my-notes/blob/master/microservices/EventSource_Advantages.JPG)

EventSource_Drawbacks.JPG

EventSource_Drawbacks1.JPG

## Transactional outbox
- https://microservices.io/patterns/data/transactional-outbox.html
# Service Discovery

# Circuit Breaker
- https://www.youtube.com/watch?v=ADHcBxEXvFA

- Hystrix

- Resilience4j

# Chaos Monkey

- https://www.youtube.com/watch?v=7sQiIR9qCdA : Chaos Monkey for Spring Boot Demo

# Netflix ZUUL API GATEWAY

- https://www.youtube.com/watch?v=sPgwbt7iREk


# Monolith to microservices

- https://github.com/himkak/my-notes/blob/master/microservices/MonolithToMicroservices.md

