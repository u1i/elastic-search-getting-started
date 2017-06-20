# Getting started with [Elastic Search](https://github.com/elastic/elasticsearch)

## Run it with Docker

`docker run -p 9200:9200 -e "http.host=0.0.0.0" -e "transport.host=127.0.0.1" docker.elastic.co/elasticsearch/elasticsearch:5.4.1`


## Access Elastic Search via GUI

http://localhost:9200/

User: elastic
Password: changeme

## Access via Curl

`curl --user elastic:changeme -X GET http://localhost:9200/`

## Create an Index

`curl --user elastic:changeme -XPUT 'localhost:9200/test?pretty' -H 'Content-Type: application/json' -d'
{
    "settings" : {
        "index" : {
            "number_of_shards" : 3, 
            "number_of_replicas" : 2 
        }
    }
}
'`

## Adding data

`curl --user elastic:changeme -XPUT 'localhost:9200/test/data/1' -H 'Content-Type: application/json' -d'
{
    "hellouser" : "super trouper",
    "message" : "trying out Elasticsearch"
}
'`

## Show all documents in an index

`http://localhost:9200/my-index/_search?pretty=true&q=*:*`

## Search

`http://localhost:9200/_search?pretty=true&q=mysearchstring`