# Docker Command Summary


## Info Commands
| Command | Description |
|----|---|
| docker -v| check docker version|
| docker info | display generic docker enviornemnt information
| docker container ls | see list of running containers|
| docker container ls -a | see list of all containers|
| docker container ls -l | only see recent contianer
| docker image ls | see list of images |
| docker images | see list of images |
| docker network ls | list all networks |
| curl localhost:8080/hello | possibility to debug |
| docker logs <container_id> | view log of a container|
| docker logs -f <container_id> | view logs in follow mode of container|
| docker ps --format "{{.ID}} {{.Ports}}" | formated output of ps command|
| docker ps -a --format "Id: {{.ID}} Name: {{.Names}}" | other formated output |
| docker ps --no-trunc | run command without truncation|
| docker container inspect <container_name> | view more details about container|
| docker restart <container_name> | restart a container |
| docker history <image_name> | to validate history of image |


## Run Commands

| Command | Description |
|----|---|
| docker run <container_name> | run/download container|
| docker run -d <container_name> | run container in detached mode|
| docker run -d -p 8080:8080 <container_name> | run container with port configuration first external second internal port |
| docker run -d -p 8081:8080 -e PROPERTY=Stuttgart <container_name> | Pass Environment Variable with the container |
| docker run -d -p 8082:8080 -e PROPERTY=Stuttgart-Entwicklertag --name <new_name> <container_name> | Command to run container with a specifi name|
| docker run -d -p 8080:8080 --network <networkname> --name <container_name> <image_name> | connect a container directly to a network |
|docker run --name <container_name> -p 5432:5432 -e POSTGRES_PASSWORD=<new_password> -e POSTGRES_USER=<user> -e POSTGRES_DB=<db_name> -d postgres:latest | command to run a postgres container |
|docker run --name <container_name> -p 5432:5432 -e POSTGRES_PASSWORD=<new_password> -e POSTGRES_USER=<user> -e POSTGRES_DB=<db_name>  -v <volume_name>:/var/lib/postgresql/data -d postgres:latest | command to run a postgres container and attacht it to a volume |


## Stop and  Remove

| Command | Description |
|----|---|
| docker rm <_id_> | remove container based on id (first three characters enough)|
| docker stop <container_name> | stopping container, necessary before rm|#
| docker ps -q \| xargs docker stop | stop all running containers|
| docker ps -a -q \| xargs docker rm | remove all containers|


## Exec and modifiy container
| Command | Description |
|----|---|
| docker exec -it <container_name> /bin/bash  | run container in interactive mode|
| exit | exiting from interactive container|
| docker cp message <contianer_name>:/<targer_directory> | copy file into the container|
| docker commit <container_name> <image_name>:<version_number> | save modifications of container in form of an image|
| docker exec -it <container_name> psql -h <host> -U <user> <database> | Access the psql service in psql container |


## Dockerfiles
| Command | Description |
|----|---|
| docker build -f <Dockerfile> -t <image_tag>:<_version_> . | Create Image from Docker file| 



## Network

|Command | Description |
|---|---|
| docker network | overview about network commands |
| docker network create <networkname> | create a network|
| docker network connect <networkname> <containername> | connect a container to a network|
| docker network inspect <networkname> | inspecting a network |
| docker network rm <networkname> | remove a network |
| docker network ls | list all networks |

## Volumes

|Command | Description |
|----|---|
| docker volume create <volume_name> | Create a volume |
| docker volume rm <volume_name> | Delete a volume |
| docker volume list | list all volumes | 


## Linux Stuff
| Command | Description |
|----|---|
| ls -ltr Dockerfile* | List all Dockerfiles in a directory|
| ping <container_name> | Inside Container Ping other container |
