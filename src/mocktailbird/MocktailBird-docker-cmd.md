## Mocktail.Bird docket setup for developer

#### Start MongoDb Instance on local
```cmd
docker run -p 27017:27017 --name mocktail-bird-mongo -d mongo:3.6.11-stretch
```


#### Image generation from dockerfile
```cmd
docker build -t mocktail-bird-dev -f mocktailbird-dev-JDK11.Dockerfile .

```

#### Logging into image created
```cmd
docker run -it mocktail-bird-dev /bin/bash
```

#### Contianer creation from images
```cmd
docker run -it --name mockatail.bird-dev mocktail-bird-dev
```

#### Logging into Container created
```cmd
docker exec -it mockatail.bird-dev /bin/bash
```


#### Local setup
```cmd
docker build -t local-dev -f Local-dev.Dockerfile .

docker run -p 27017:27017 --name mocktail-bird-mongo -d mongo:3.6.11-stretch

docker run -it -p 9080:9080 --network=mocktail-bird-mongo --name mockatail.bird-dev  local-dev

docker run -it -p 9080:9080 --network=mocktailbird_net-app-mongo --name mockatail.bird-dev mocktail-bird-dev

docker network create -d bridge mongodb


docker run -it -p 27017:27017 --network=mongodb \
    --mount source=mocktailvol1,target=/data/db  \
    --name mocktail-bird-mongo mongo:3.6.11-stretch

docker build -t local-dev -f Local-dev.Dockerfile .

docker run -it --network=mongodb -p 9080:9080 --name mockatail.bird-local-dev local-dev

docker run -it --network=mongodb -p 9080:9080 --name mockatail-bird-qa mocktail-bird:qa


docker build -t mocktail-bird -f mocktailbird-dev-JDK11.Dockerfile .
```
