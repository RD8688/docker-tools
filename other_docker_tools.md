### Nexus
-----------------------------

Reference : https://hub.docker.com/r/sonatype/nexus3/
 * run this command `docker run -p 8080:8080 -p 50000:50000 -v /Users/deepak/jenkins-data:/var/jenkins_home jenkins`

#### H2 datbase
-----------------------------
```
docker pull oscarfonts/h2
docker run -d -p 1521:1521 -p 81:81 -v /Users/deepak/docker_dirs/h2_database:/opt/h2-data --name=h2_database oscarfonts/h2
```

Ref:  https://github.com/oscarfonts/docker-h2

#### Prometheus
------------------
```
docker pull prom/prometheus
docker run -p 9090:9090 prom/prometheus
```

#### Run metabase on docker
```
docker run -d -p 3000:3000 -v metabase-data:/tmp -e "MB_DB_FILE=/tmp/metabase.db" --name metabase metabase/metabase
```



#### Install Kafka
```
docker run -p 2181:2181 -p 9092:9092 -d --env ADVERTISED_HOST=`docker-machine ip \`docker-machine active\`` --env ADVERTISED_PORT=9092 spotify/kafka
```


####Install ES
```
docker run --name elasticsearch  -d -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -v elasticsearch-data:/usr/share/elasticsearch docker.elastic.co/elasticsearch/elasticsearch:6.2.2
```

####Install Mongo(27017)
```
docker run --name mongo-db -p 27017:27017 -v mongo-data:/data/db  -d mongo
```