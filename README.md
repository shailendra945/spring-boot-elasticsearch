# spring-boot-elasticsearch
we will explore various concept of elasticsearch with spring boot

#Discovery tools commands : 

GET /_cluster/health
GET /_cat/nodes?v
GET /_cat/indices?v&expand_wildcards=all 
GET /_cat/shards?v
 
PUT /pages

DELETE /pages      

PUT /products
{
    "settings":{
        "number_of_shards":2,
        "number_of_replicas":2
    }
}

POST /products/_doc
{
    "name":"Coffe Maker"
    "price":50,
    "instock":true,
    "quantity":100
}

PUT /products/_doc/101
{
"name":"Toaster"
"price":40,
"instock":true,
"quantity":200
}

GET /products/_doc/101

POST /products/_update/101
{
    "doc":{
    "instock":false
    }
}

add new field to document
POST /products/_update/101
{
    "doc":{
     "tags":["electronic"]
    }
}

note: documents are immutable in elasticsearch
mean new document will be created assigned the same id and put into the same index 
when you update or add a field in document.