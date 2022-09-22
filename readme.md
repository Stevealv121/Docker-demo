Simple js project with mongo to demo docker

# Docker commands

docker network create mongo-network(name)

## start mongo db container

docker run -d \
-p 27017:27017 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
--name mongodb \
--net mongo-network \
mongo (imageName)

## start mongo-express container

docker run -d `
-p 8081:8081 `
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin `
--net mongo-network `
--name mongo-express `
-e ME_CONFIG_MONGODB_SERVER=mongodb `
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password `
mongo-express

# Docker compose example

see file mongo.yaml

## Commands

```
docker-compose -f mongo.yaml up
``` 

# Creating a docker image

## command

```
docker build -t simplejs:1.0 .
```

## essential files

copy essential file to a directory called app

## running on same net

```
docker run -d `
 -p 3000:3000 `
 --net docker-demo_default `
 simplejs:1.0
```