## Docker Cheats

#### List Docker CLI commands

```cmd
$ docker
$ docker container --help
```

#### Display Docker version and info

```cmd
$ docker --version
$ docker version
$ docker info
```

#### Execute Docker image

```cmd
$ docker run hello-world
```

#### List Docker images

```cmd
$ docker image ls
```

#### List Docker containers (running, all, all in quiet mode)

```cmd
$ docker container ls
$ docker container ls --all
$ docker container ls -aq
```

#### This creates a Docker image, which we’re going to name using the --tag option.

* Use -t if you want to use the shorter option.
```cmd
$ docker build --tag=friendlyhello .
```

* Note how the tag defaulted to latest. The full syntax for the tag option would be something like

  >  --tag=friendlyhello:v0.0.1
#### Set proxy server, replace host:port with values for your servers

> ENV http_proxy host:port

> ENV https_proxy host:port

#### Run the app, mapping your machine’s port 4000 to the container’s published port 80 using -p:

```cmd
$ docker run -p 4000:80 friendlyhello
```

#### Run the app in the background, in detached mode:

```cmd
$ docker run -d -p 4000:80 friendlyhello
```

#### Use docker container stop to end the process, using the CONTAINER ID, like so:
```cmd
$ docker container stop 1fa4ab2cf395
```

#### Run docker tag image with your username, repository, and tag names so that the image uploads to your desired destination.
```cmd
$ docker tag image username/repository:tag
```

#### Upload your tagged image to the repository:

```cmd
$ docker push username/repository:tag
```
#### All at one place
```cmd
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
docker run -it mocktail-bird-dev /bin/bash     # Logging into image created
docker exec -it mockatail.bird-dev /bin/bash   # Logging into Container created
```
#### A docker-compose.yml file is a YAML file that defines how Docker containers should behave in production
```cmd
docker stack ls                                            # List stacks or apps
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker service ls                 # List running services associated with an app
docker service ps <service>                  # List tasks associated with an app
docker inspect <task or container>                   # Inspect task or container
docker container ls -q                                      # List container IDs
docker stack rm <appname>                             # Tear down an application
docker swarm leave --force      # Take down a single node swarm from the manager
```

#### Remove images and containers
```cmd
docker rmi $(docker images)
docker rm $(docker ps -a)
```
#### Run cassandra
```cmd
docker run --name cassandra-db --network some-network -d cassandra:tag
```
