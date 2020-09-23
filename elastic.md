# Elasticsearch Cheat Sheet

## Creating an index
### Kibana Console
    PUT testindex
### cURL
```
curl -X PUT "localhost:9200/testindex?pretty"
```