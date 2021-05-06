# BookMyShow

## Functional Requirements
- User should be able to see the Cinema Halls based on Location
- User should be able to see the Movies shows based on Cinema Hall
- User should be able to see the diff types of available tickets based on selected movie show
- User should be able to select seat from the available seats
- User Should be able to book the ticket / multiple tickets, by making online payment
- User should get notification/email on successful booking

## NFR
- Consistency of data
- multiple users should no be able to book same ticket
- Durability

## Back of the envelop calculation
**Database size**
- Only for India
	- No of cinema halls :~ 1000
	- Every cinema hall has screens : 5
	- Every screen has shows : 10
	- In every show, no of seats available : 100
	- size per seat per show : 5 b
					Booked by
					seat id : row_col
	- Total Data to represent the seats : 1000*5*10*100*5=25E6b = 25GB
	- Total data to capture movies information

**Bandwidth**
- Biggest response : show information : 10 kb
- Max active sessions at any moment : 10,000
- R:W ratio : 9:1
- 9000 * 100 = 9E4 kb = 10 MB/sec


## API
- get all the available locations : GET /locations
- get all the cinema halls of a specific location : GET /locations/<locationId>/halls
- get all the movies in that cinema hall : GET GET /locations/<locationId>/halls/<hallId>/movies : movie info: shows, screen etc
- avbl tickets for a movie show : /locations/<locationId>/halls/<hallId>/movies/<movieId>/show/<showId> : return avbl tickets
- select seat : POST : shows/seats/lock : Request :{showId:"", seatsIds:[]}

## Data Model

Cinema Hall :
	hall name
	location
	id
	no of screens

Screen:
	id
	cinema hall id
	no of seats

Show
	id
	screen id
	movieId
	start date time
	end date time
	
Movie:
	id
	name
	actors..
	
Seat
	id : row_col
	showId : as the price of the seat can vary depending on show (morning/evening), so showId being used as FK
	seat price
	status : available/booked

Ticket:
	ticket id
	seatId
	userId
	
Ticket Locking/Reserving : 
	lock time
	ticket id (unique)

Ticket Booking:
	ticketId
	booking status : booked
	payment status
	Booked by : 

## How to keep the consistency of ticket booking
	This table helps us to lock on the ticket as soon as a user selects a ticket. If the ticket is not booked within specific time(eg 10 mins), the ticketId to be removed from this table. 
	We can also use redis for this. To take the lock, store the ticketId in redis with a TTL of 10 mins. If the ticket is booked save this info in ticket booking table. 
	Available tickets page is loaded by referring the seat table and 
	If two users go to select same seat, suppose the request of U1 comes first and we loack ticket for U1. U2 request comes and we check in redis the smae ticket is already locked, so u2 gets the exception. If u1 doesnt books within next 10 mins ticket will be freed.
	

## DB type to be used
- There are 2 kinds of data
	- Transactional Data : Ticket booking
	- Non transactional data
- As Transactional data is less we can go with relational DB (MySql)
- For rest of the data, we dont ned any ACID properties, so we can go with columnar DB
- Redis is being used to cache read results

## High Level components

- Movie view service : serves the read APIs : cinema halls, movies, available tickets
- Ticket reservation service : used for write operations. Like lock a seat, book the ticket
- API Gateway : Handles Orchestration (decides to which MS the request should be fwd to)
- Notification service : For sending email/sms to user
- queue : To publish ticket booked event. Multiple other tasks can be trigerred on ticket being booked.
- CDN : Used to store the 
- DNS : Depending on the url fwd the request to nearest CDN or to API Gateway
- Redis : caches the responses which dont change through out the day. Helps to take lock and reserve a seat.
- cassandra : For storing the non transactional data. As we want availability for this data, so cassandra is a good option
- MySql : Read Replicas, stores the transactional data.
- S3 : Stores the images, trailers of movies


![Architecture](https://github.com/himkak/notes/blob/master/SystemDesign/BookMyShow/BookMyShow.jpg)