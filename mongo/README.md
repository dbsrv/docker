Build the MongoDB image using Docker

Format: docker build --tag/-t <user-name>/<repository> .

Example:

$ docker build --tag my/repo .

Once this command is issued, Docker will go through the Dockerfile and build the image. The final image will be tagged my/repo.

# Basic way
# Usage: docker run --name <name for container> -d <user-name>/<repository>
$ docker run -p 27017:27017 --name mongo_instance_001 -d my/repo

# Dockerized MongoDB, lean and mean!
# Usage: docker run --name <name for container> -d <user-name>/<repository> --noprealloc --smallfiles
$ docker run -p 27017:27017 --name mongo_instance_001 -d my/repo --smallfiles

# Checking out the logs of a MongoDB container
# Usage: docker logs <name for container>
$ docker logs mongo_instance_001

# Playing with MongoDB
# Usage: mongo --port <port you get from `docker ps`>
$ mongo --port 27017

# If using docker-machine
# Usage: mongo --port <port you get from `docker ps`>  --host <ip address from `docker-machine ip VM_NAME`>
$ mongo --port 27017 --host 192.168.59.103
