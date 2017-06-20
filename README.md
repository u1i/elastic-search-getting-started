# Getting started with Elastic Search

## Run it with Docker

`docker run -p 9200:9200 -e "http.host=0.0.0.0" -e "transport.host=127.0.0.1" docker.elastic.co/elasticsearch/elasticsearch:5.4.1`


## Access Elastic Search via GUI

http://localhost:9200/

User: elastic
Password: changeme

## Access via Curl

`curl --user elastic:changeme -X GET http://localhost:9200/`


