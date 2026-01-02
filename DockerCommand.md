# Docker Images

1. Build an image from a Dockerfile:
   docker -t build image_name path_to_dockerfile

Example

docker -t build myapp .

2. List all local images:
   docker images

Example

docker ls image

3. Pull an image from Docker Hub:
   docker pull image_name:tag

Example

docker pull nginx:latest

4. Remove a local imag
   docker rmi image_name:tag

Example

docker rmi myapp:latest

5. Tag an image:
   docker tag source_image:tag new_image:tag

Example

docker tag myapp:latest myapp:v1

6. Push an image to Docker Hub:
   docker push image_name:tag

Example

docker push myapp:v1

7. Inspect details of an image:
   docker inspect image image_name:tag

Example

docker inspect image myapp:v1

8. Save an image to a tar archive:
   docker -o save image_name.tar image_name:tag

Example

docker -o save myapp.tar myapp:v1

9. Load an image from a tar archive:
   docker -i load image_name.tar

Example

docker -i load image_name.tar

10. Prune unused images:
    docker prune image

# Docker Container

1. Run a container from an image:
   docker run container_name image_name

Example

docker run myapp

2. Run a named container from an image:
   docker --name run container_name image_name:tag

Example

docker --name run my_container myapp:v1

3. List all running containers:
   docker ps

4. List all containers (including stopped ones):
   docker -a ps

5. Stop a running container:
   docker stop container_name_or_id

Example

docker stop my_container

6. Start a stopped container:
   docker start container_name_or_id

Example

docker start my_container

7. Run container in interactive mode:
   docker -it run container_name_or_id

Example

docker -it run my_container

8. Run container in interactive shell mode
   docker -it run container_name_or_id sh

Example

docker -it run my_container sh

9. Remove a stopped container:
   docker rm container_name_or_id

Example

docker rm my_container

10. Remove a running container (forcefully):
    docker -f rm container_name_or_id

Example

docker -f rm my_container

11. Inspect details of a container:
    docker inspect container_name_or_id

Example

docker inspect my_container

12. View container logs:
    docker logs container_name_or_id

Exampl
docker logs my_container

13. Pause a running container:
    docker pause container_name_or_id

Example

docker pause my_container

14. Unpause a paused container:
    docker unpause container_name_or_id

Example

docker unpause my_container

# Docker Volumes and Network

1. Create a named volume:
   docker create volume volume_name

Example

docker create volume my_volume

2. List all volumes:
   docker ls volume

3. Inspect details of a volume:
   docker inspect volume volume_name

Example

docker inspect volume my_volume

4. Remove a volume:
   docker rm volume volume_name

Example

docker rm volume my_volume

5. Run a container with port mapping:
   docker --name -p run container_name host_port:container_port
   image_name

Example

docker --name -p run my_container 8080:80 myapp

6. List all networks:
   docker ls network

7. Inspect details of a network:
   docker inspect network network_name

Example

docker inspect network bridge

8. Create a user-defined bridge network:
   docker create network network_name

Example

docker create network my_network

9. Connect a container to a network:
   docker connect network network_name container_name

Example

docker connect network my_network my_container

10. Disconnect a container from a network:
    docker disconnect network network_name container_name

Example

docker disconnect network my_network my_container

# Docker Compose

1. Create and start containers defined in a docker-
   compose.yml file:
   docker up compose
   This command reads the docker-compose.yml file and
   starts the defined services in the background.

2. Stop and remove containers defined in a docker-
   compose.yml file:
   docker down compose
   This command stops & removes the containers, networks,
   and volumes defined in the docker-compose.yml file.

3. Build or rebuild services:
   docker build compose
   This command builds or rebuilds the Docker images for the
   services defined in the docker compose.yml file.

4. List containers for a specific Docker Compose
   project:
   docker ps compose
   This command lists the containers for the services defined
   in the docker-compose.yml file.

5. View logs for services:
   docker logs compose
   This command shows the logs for all services defined in the
   docker-compose.yml file.

6. Scale services to a specific number of containers:
   docker up -d --scale compose
   service_name=number_of_containers

Example

docker up -d --scale compose web=3

7. Run a one-time command in a service:
   docker run service_name compose command

Example

docker run web npm compose install

8. List all volumes:
   docker ls volume
   Docker Compose creates volumes for services. This
   command helps you see them.

9. Pause a service:
   docker pause service_name volume

10. Unpause a service:
    docker unpause service_name volume

11. View details of a service:
    docker ps service_name compose

# Latest Docker

1. Initialize Docker inside an application
   docker init

2. Watch the service/container of an application
   docker watch compose
   It watches build context for service and rebuild/refresh
   containers when files are updated
