```json
#fetches all documents
GET _search
{
  "query": {
    "match_all": {}
  }
}

# Single document post/insert
POST /user/details
{
  "name":"him",
  "age":31,
  "GENDER":"M"
}

#Multiple documents post/insert
POST /user/details/_bulk
{"index":{"_id":1}}
{"name":"him1","age":31, "GENDER":"M"}
{"index":{"_id":2}}
{"name":"him2","age":32, "GENDER":"F"}
{"index":{"_id":3}}
{"name":"him3","age":33,"GENDER":"M"}


#fetches all user details documents
GET /user/details/_search

#Update
PUT /user/details/tUanumkBK84ZjeYeVNqG
{
  "age": 32
}

#Delete
DELETE /user/details/tUanumkBK84ZjeYeVNqG


#fetches specific user details documents
GET /user/details/_search
{
  "query":{
    "match":{
      "GENDER":"F"
    }
  }
}

#execute sql query
GET /_xpack/sql?format=txt
{
  "query": "select name from user where age > 31"
}


# TO find the mapped datatype
GET /user/_mapping/details

```