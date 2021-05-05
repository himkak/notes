# Instagram

## Features
- Upload images
- user follow other users
- Generate a feed

## NFR
- scale
- Read heavy solution

## Numbers
- 10 M users monthly basis
- 2 photos per user per month
- 5mb every photo size
**storage size to store images** : 10 M * 2*5 = 10^8 mb = 100 TB = 1.2 PB

**Real Numbers**
- 400 Million users
- 4+ billion likes
- 100 M photos/videos uploads
- Top account : 110 Million followers

## Data model

- Relational data 

**User**
- id : primary key, sequential
- name
- email
- location

**Photo**
- id
- user_id
- url
- caption
- location

**Users following**
- from_user_id
- to_user_id

## Database behaviour
- Eventual Consistent, with some latency
- Relational, read replicas : data to be stored : user, media, friendship
- cassandra : user feed, activities

## System Design

![System Design](https://github.com/himkak/notes/blob/master/SystemDesign/Instagram/SystemDesign.JPG)


# References

- https://www.youtube.com/watch?v=VJpfO6KdyWE 
