## Apache Solr

Solr is highly reliable, scalable and fault tolerant, providing distributed indexing, replication and load-balanced querying, automated failover and recovery, centralized configuration and more. Using a Dockerfile from a older public version and tweaking it to a new version build contained within this repo.

```
docker run -it -p 8983:8983 htmlgraphic/solr:5.3.1
```

(connect to running container)

```
eval "$(docker-machine env default)"
```

(within the running container)

```
solr/bin/solr create -c test
cd solr
```

Let's load thousands of documents so we have data to play with.

```
bin/post -c test example/exampledocs/*.xml
bin/post -c test docs/
```


Test this out within your browser, your ip address might vary but if you only have one Docker node this will be the default IP address:
http://192.168.99.100:8983/solr/test/browse


Search for this information as this is sorta unique (**version 1.7.0_79**)  


## Contribute

- Fork
- Improve
- Document your improvements
- Commit, push and make a pull-request