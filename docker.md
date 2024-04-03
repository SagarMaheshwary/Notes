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
- We can use docker compose to run multiple containers at the same time. These containers can also communicate with each other.

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

- **-p** to bind a host machine port to container (port forwarding)
- **-v** to define volume
- **-e** to set environment variables
- **-d** to run a container in detached mode (in background)
- **--name** to assign a name to the container

Syntax:

```bash
docker run -p host-port:container-port --name container-name -v host-directory:container-directory -e CONTAINER_VARS=value image-name:tag
```

Running a PostgreSQL (version 12) container:

```bash
docker run -p 5432:5432 --name postgres -e POSTGRES_PASSWORD=password postgres:12
```

Running the container in detached mode:

```bash
docker run -d -p 5432:5432 --name postgres -e POSTGRES_PASSWORD=password postgres:12
```

Creating volume to keep data synced to the host machine:

```bash
docker run -d -p 5432:5432 --name postgres -v /home/ubuntu/postgres-data:/var/lib/postgresql/data -e POSTGRES_PASSWORD=password postgres:12
```

Stopping a container:

```bash
docker container stop postgres
```

You can also stop the container by it's id (which can be found in containers list):

```bash
docker container stop 65941b27a8ec
```

Also note that it is not mandatory to pass the complete id and just few starting characters are enough:

```bash
docker container stop 659
```

Force remove a container:

```bash
docker container stop -f 659
```

You can also autoremove the container once it's stopped using the **--rm** flag:

```bash
docker run --rm -p 5432:5432 --name postgres -e POSTGRES_PASSWORD=password postgres:12
```

#### DOCKER IMAGE

We can create custom images for our applications with **Dockerfile**. Below is an example of a simple nodejs application:

```Dockerfile
FROM node:18-alpine

WORKDIR /app

COPY ./package*.json ./

RUN npm i

COPY . /app

CMD ["npm", "start"]

```

We can build this image using docker **build** command, passing image name with **-t** flag and directory path for **Dockerfile** (**.** in our case for current directory)

```bash
docker build -t nodeapp .
```

#### Docker Compose

Docker compose is a tool used for running and managing multiple docker containers.

Starting all the containers defined in docker compose:

```bash
docker compose up
```

Above command will expect the **docker-compose.yml** file to be in the current directory but we also specify the path with **-f** flag:

```bash
docker compose -f docker-compose.yml up
```

Stopping containers:

```bash
docker compose -f docker-compose.yml down
```

Restarting containers:

```bash
docker compose -f docker-compose.yml  restart
```

Stop and Remove all the containers:

```bash
docker compose -f docker-compose.yml down
```
