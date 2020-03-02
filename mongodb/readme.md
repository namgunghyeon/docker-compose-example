# Mongodb cluster
## PSS Primary -Secondary - Secondary

froked from https://github.com/minhhungit/mongodb-cluster-docker-compose

## start
```bash
docker-compose up -d
```


```bash
docker-compose exec configsvr01 sh -c "mongo < /scripts/init-configserver.js"

docker-compose exec shard01-a sh -c "mongo < /scripts/init-shard01.js"
docker-compose exec shard02-a sh -c "mongo < /scripts/init-shard02.js"
docker-compose exec shard03-a sh -c "mongo < /scripts/init-shard03.js"
```

## connection
mongodb://180.16.101.11:27017,180.16.101.12:27017/MyDatabase
