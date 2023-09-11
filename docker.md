# DOCKER

### NOTES

- Docker packages software with all the necessary dependencies, configuration, system tools, and runtime that can run on any hardware.
- Unlike a virtual machine, docker uses the host OS kernel which makes it very fast.
- A Dockerfile is a template for building images.
- An image is a template for building containers.
- NOTE: an image can only have one **CMD** command.
- We can use -p flag to do port forwarding when running a container.
- By default, all the files created in a container willl disappear once it's stopped so we can use volumes that bind directories/files from host filesystem to container.
- Each container should only run one process. e.g a container for nodejs application (backend) and another container for mongodb (Database).
- We can use docker compose to run multiple containers at the same time. while these containers can also communicate with each other.
- @TODO: Networks

### USAGE EXAMPLES

List containers

```bash
docker container ls
```

List all containers (including exited)

```bash
docker container ls -la
```

List all images

```bash
docker image ls
```

Run a container

```bash
docker run hello-world
```

You can use:

- **-p** flag to bind a host machine port to container (port forwarding)
- **-v** to define volumes
- **-e** to set environment variables
- **--name** to assign a name to container

Below is an example of running a PostgreSQL container:

```bash
docker run --rm -p 5432:5432 --name postgres -v /home/ubuntu/postgres-data:/var/lib/postgresql/data -e POSTGRES_PASSWORD=password postgres:12
```

#### Build an Image

We can built custom images for our applications with **Dockerfile**. Below is an example of a nodejs application:

```Dockerfile
FROM node:18-alpine

WORKDIR /app

COPY ./package*.json ./

RUN npm i

COPY . /app

CMD ["npm", "start"]

```

build an image with docker: (where **.** is the path to our Dockerfile which is the current directory)

```bash
docker build -t nodeapp .
```

#### Docker Compose

@TODO
