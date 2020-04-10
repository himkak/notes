# WhatsApp System Design

## Use Cases

- One to one chatting
- Group chatting
- User online status
- Heart beat

## Common features
- History info
- Log in from multiple devices
- Friendship / Contact book

## High Level Components


## Approach 1
- https://www.youtube.com/watch?v=zKPNUMkwOJE : System Design : Design messaging/chat service like Facebook Messenger or Whatsapp : Tushar Roy - Coding Made Simple

### One to one chatting & Last seen**

#### Connection Service
- To Maintain connections with clients
- When user comes online, it connects to connection service. Client opens the connection
- If App is open it send s heart beat over the same connection, in a specified duration. This is used to inform firends he is online.

**What kind of connection should we consider**
- push or pull : push, as on pull client will have to work very hard
	- https://www.youtube.com/watch?v=8D1NAezC-Dk : Difference between Client Polling vs Server Push in Notifications

- in pooling mode we have options of long http pooling, but client has to keep on pooling. so this is not preferred.

- In push mode which protocol : websocket or xmpp : 
	- Both are bidirectional protocols.
	- websockets, as xmpp is xml based, so the msgs are big and it consumes lot of bandwidth.
	- https://medium.com/@thinkwik/web-sockets-vs-xmpp-which-is-better-for-chat-application-113e3520b327
	- websocket is fast, xmpp is secure

- This service keeps on websocket connection with client. 
- There will be a load balancer bewteen the client and connection service. 
- As sson as user logs in a websocket connection is made with the server. this is trigerred by the client.
- If the connection service goes down, the client comes to know, as the websocket connection breaks. At this moment the client again triggers a new websocket connection with the avaibale connection server.
- At that moment the client again sends the request, to start a new websocket connection.
- server can maintain hashtable to manage the connections, with key as userId and value as connection object. [why store as connection will always be open]

**Last Seen**
- When this websocket connection is open, both client and server keeps on sending heart beat. 
- This also helps in storing last seen details.
- As the last seen information keeps on updating, after every heart beat, connection service keeps on updating in the DB. As this data needs fast read and write we can store it in redis cache.
- The user, server and last seen can be stored as key value data strcuture.

```
"userId" = { "server":"", "lastSeen":""}
```
- When the user closes the app, the client stops sending the heart beat. As the connection server, doesnt gets the heart-beat, so it doesnt updates the last seen.

![Approach 1](https://github.com/himkak/notes/blob/master/SystemDesign/whatsApp_Approach1.jpg)


#### Business Flow
- User A sends a message to user B. User B receives the message.
	- When User A sends the message if he is online, his message is uploaded, and he gets 1 tick
	- When User B connects to the internet, he will receive the message nitification. User A will get 2 ticks
	- When User B opens the message, the app sends a message that it has been read. User A gets 2 blue ticks.
	
#### Tech flow
**Receiver is online**
- When the user A sends a message to user B, the message first reaches the connection service. 
- The connection service checks the redis cache for last seen details, if the user B is online, it fetches the server details and sends the message to that specific server.

- message params:
```
fromUser
toUser
sentTime
message
```

**Receiver is offline**
- If the user B is ofline, this message in stored in cassandra DB.
- When user B comes online, and makes the connection to server, the server checks the cassandra DB and if there are some messages for user B, the server fetches the messages and sends that to user B.

#### DB Structure

##### Relational
- conversion table: conversation id, encryptedMessage, time
- user conversation table : userId, conversiation Id, encryption key
- unread table : 



## Approach 2

- https://www.youtube.com/watch?v=vvhC64hQZMk&t=1451s : Whatsapp System Design: Chat Messaging Systems for Interviews : Gaurav Sen

### Components

- Load Balancer : To distribute the load. TO which server the client should connect.
- Connection Service : Just to manage the connection
- message management service (MMS : It manages the last seen. Depending on the last seen, on which server, it sends the message to that server.
- last seen : 
- Group service : manages the group related information

![Approach 1](https://github.com/himkak/notes/blob/master/SystemDesign/whatsApp_Approach2.jpg)

- In this aproach, we extnd the previous approach.
- The connection service just manages the connections.
- As soon as it gets the message, it forwards this message to message management service (MMS).
- Tracking the heartbeat messages, the MMS manages the last seen details.
- MMS checks if the user is online/ofline. If the user is online sends the message to specific connection service. Connection service sends the message to the receiver.
- If the user is offline MMS saves the message to DB.
- When the user comes online, MMS gets the heartbeat message. As soon as it gets the hearbeat message, it checks if there are any messages in the DB for that user, if yes sends the message to that user.
- The ticks are done based in the acknowledgement received.
- As sson as MMS gets the ack of receiver received the message, it deletes the message from its DB.

## DB
- In addition to previous tables
- groupDetails : groupId, userId





## Image share







## References


- https://github.com/DreamOfTheRedChamber/system-design/blob/master/messenger.md (*****)

- protocol : XMPP  /  WobSocket
- https://www.youtube.com/watch?v=6YhMOFS04kA : XMPP Tutorial : The Friendly Introduction
- https://medium.com/@thinkwik/web-sockets-vs-xmpp-which-is-better-for-chat-application-113e3520b327 : Web Sockets vs. XMPP: Which Is Better For Chat Application?

- https://www.youtube.com/watch?v=8D1NAezC-Dk : Difference between Client Polling vs Server Push in Notifications

- https://leetcode.com/discuss/interview-question/system-design/124613/design-question-a-scalable-chat-application-on-phone-browsing

- https://docs.ejabberd.im/developer/extending-ejabberd/architecture/ : Architecture of EjabberD, chat as a service application

- https://www.codementor.io/@vigneshwaranb/why-enterprise-chat-apps-isn-t-built-on-server-side-database-like-hangouts-slack-hipchat-10kqdft9xg

- https://www.youtube.com/watch?v=zKPNUMkwOJE

- https://medium.com/hackernoon/how-to-build-your-own-real-time-chat-app-like-whatsapp-9d1d058afd5b : How to Build your Own Real-time Chat App like WhatsApp?
- contus fly is a company that provides the solution to build chat apps



**Common Features**
- user login
- One to one message
- Group Message
- Message delivery status
- Deliver Images Videos

**Components**
- Authentication API, for login, logout & registration
- Account Management API
- Message Exchange for real time messaging of all online devices
- Storage for multi-media contents
- Storage for message histories
- Storage for unread messages

#### Whatsapp 

- Ejabbered server


- https://www.wired.com/2015/09/whatsapp-serves-900-million-users-50-engineers/ [TODO]
- https://developers.facebook.com/videos/f8-2016/a-look-at-whatsapp-engineering-for-success-at-scale/ [TODO]
- http://highscalability.com/blog/2014/2/26/the-whatsapp-architecture-facebook-bought-for-19-billion.html [TODO]
- https://www.youtube.com/watch?v=jN1pnBVIj7M (**)
- https://www.youtube.com/watch?v=vvhC64hQZMk (***)

- https://www.cronj.com/blog/how-to-develop-chat-system-design-like-facebook-messenger

- http://www.ijcset.com/docs/IJCSET16-07-07-015.pdf

- https://www.youtube.com/watch?v=wDk6l3tPBuw : Scaling to Millions of Simultaneous Connections: Rick Reed

- https://www.youtube.com/watch?v=L7LtmfFYjc4
- https://medium.com/codingurukul/whatsapp-engineering-inside-1-1ef4845ff784 [bakwas]



**Technology used:**
- Erlang
- xmpp protocol
- FreeBSD OS
- YAWS: (Yet Another Web Server)

#### facebook messenger

- https://github.com/himkak/library/blob/master/system%20design/GrokkingTheSystemDesign_Educative_Designing%20Facebook%20Messenger.pdf



#### Slack

- https://www.youtube.com/watch?v=WE9c9AZe-DY

