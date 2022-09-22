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

