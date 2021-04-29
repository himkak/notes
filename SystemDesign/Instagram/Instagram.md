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

## System Design

![System Design](https://github.com/himkak/notes/blob/master/SystemDesign/Instagram/SystemDesign.JPG)