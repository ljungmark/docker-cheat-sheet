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
|:-----|:-----|
| List images | `docker images` |
| Remove specific image(s) | `docker rmi <image_id> <image_id> ...` |
| Remove dangling images | `docker image prune` |
| Remove all unused images | `docker image prune -a` |
| Remove all images | `docker rmi -f $(docker images -q)` |
| Save an image to a .tar file| `docker save -o <path to tar file> <image name>` |
| Load an image from a .tar file| `docker load -i <path to tar file>` |


## Containers
Runnable instance of a Docker image.


### Containers: Monitor

| task | command |
|:-----| :-----|
| List running containers | `docker ps` |
| List all containers | `docker ps -a` |
| Hash of running containers | `docker ps -q` |
| Hash of all containers | `docker ps -aq` |
| Tail container logs | `docker logs -f --tail=0 <container name>`|
| Create an image of a container | `docker export -o <path to tar file> <container name>`|


### Containers: Managing

| task | command |
|:-----|:-----|
| Enter container | `docker exec -it <container name> sh/bash` |
| Open temporary container | `docker run -it --rm <image name> sh/bash` |
| Stop container | `docker stop <container name>` |
| Kill container | `docker kill <container name>` |
| Remove all stopped containers | `docker container prune` |
| Remove containers (incl. running) | `docker rm -f $(docker ps -qa)` |
| Remove unused containers older than a week | `docker container prune --filter "until=168h"` |

## Volumes
Persistent, stateful data generated and used by containers.

| task | command |
|:-----|:-----|
| List volumes | `docker volume ls` |
| Remove volume | `docker volume rm <volume name>`|
| Remove unused volumes| `docker volume prune` |
