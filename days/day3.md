# Docker
___
Index | Topic
--- | ---
**1** | Definitions
**2** | Commands
**3** | Docker file
**4** | Docker Network
**5** | Docker Compose

## Definitions

- Container: A unit of software that packages up code and all its dependencies.
  - Containers isolate software from its environment
- Image: Standalone, executable package of software that includes everything needed to run an application
  - An image becomes a container when they run on Docker Engine.

## Commands

Run file:
```bash
docker run --rm -v $(pwd):/src python:3 python /src/hello.py
```
- `--rm`: Once the container shuts down, remove the container
- `-v $(pwd):/src`: Volume. Mount a host folder into the container
- `python:3` Image name
- `python /src/hello.py` The command to run


Run python interpreter:
```bash
docker run --rm -it -v $(pwd):/src python:3 python 
```
- `--rm`: Once the container shuts down, remove the container
- `-it`: Make the container interactive
- `-v $(pwd):/src`: Volume. Mount a host folder into the container
- `python:3` Image name
- `python` The command to run

Inspect images that you have:
```
docker image ls
```

Inspect running containers:
```
docker container ls
```

## Docker file

The purpose of the docker file is to describe how an image is built and what is contained in it

```Dockerfile
FROM python:3

RUN pip3 install numpy
```

Build custom image:
```
docker build -t python_numpy .
```

## Docker Network

Enables communication between containers. Isolates the containers from the rest of the network and sets DNS entries between the containers so they can talk to each other according to their name.

Create a network:
```
docker network create yournetworkname
```

Create a container and connect it to the network:
```
docker run --rm -it --net yournetworkname --name container_name node:8 /bin/bash
```

## Docker Compose

It's a tool for defining and running multi-container docker applications. It uses a yaml file to configure application services.

With docker compose, you dont have to specify a network. WHen they are ran together in the same file, they will be networked together automatically.

Docker compose example (docker-compose.yaml):
```yaml
version: '3'
services:
  redis:
    container_name: ex1_redis
    image: redis:3.2.12
    volumes:
      - ./redis:/data
    restart: always
  mysql:
    container_name: ex1_mysql
    image: mysql:5.6
    environment: 
      MYSQL_ROOT_PASSWORD: root
    volumes:
      - ./mysql:/var/lib/mysql
    restart: always
```

Start:
```
docker-compose up
```

Start in background:
```
docker-compose up -d
```

Stop:
```
docker-compose down
```