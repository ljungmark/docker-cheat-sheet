Docker Cheat Sheet
===============

* [Images](#user-content-images)
* [Containers](#user-content-containers)
  * [Monitor](#user-content-containers-monitor)
  * [Managing](#user-content-containers-managing)
* [Volumes](#user-content-volumes)


## Images
Read-only and stateless template for Docker containers.


| task | command |
|:-----|:--------|
| All images | `docker images` |
| Remove specific image(s) | `docker rmi <image_id> <image_id> ...` |
| Remove dangling images | `docker image prune` |
| Remove all unused images	 | `docker image prune --all` |
| Remove all images	 | `docker rmi -f $(docker images -q)` |
| Save a image to a .tar file | `docker save -o <path to tar file> <image name>` |
| Load image from a .tar file | `docker load -i <path to tar file>` |


## Containers
Runnable instance of a Docker image.


### Containers: Monitor

| task | command |
|:-----|:--------|
| Running containers | `docker ps` |
| Hash of running containers | `docker ps -q` |
| All containers | `docker ps -a` |
| Hash of all containers | `docker ps -aq` |
| Tail container logs | `docker logs -f <container name>` |


### Containers: Managing

| task | command |
|:-----|:--------|
| Enter container | `docker exec -it <container name> sh/bash` |
| Kill running containers | `docker kill $(docker ps -q)` |
| Remove all exited containers | `docker container prune` |
| Remove old containers | `docker ps -a \| grep 'weeks ago' \| awk '{print $1}' \| xargs docker rm` |
| Remove all containers	 | `docker rm -f $(docker ps -qa)` |


## Volumes
Persistent, stateful data generated and used by containers.

| task | command |
|:-----|:--------|
| Running containers | `docker volume ps` |
| Remove volumes | `docker volume rm $(docker volume ls -q)` |
