Docker Cheat Sheet
===============

* [Images](#user-content-images)
* [Containers](#user-content-containers)
  * [Monitor](#user-content-containers-monitor)
  * [Managing](#user-content-containers-managing)
* [Save & Load](#user-content-save-and-load)


## Images
Monitor images

| task | command |
|:-----|:--------|
| All images | `docker images` |
| Remove specific image(s) | `docker rmi <image_id> <image_id> ...` |
| Remove dangling images | `docker image prune` |
| Remove all unused images	 | `docker image prune --all` |
| Remove all images	 | `docker rmi -f $(docker images -q)` |


## Containers
Monitor containers


### Containers: Monitor

| task | command |
|:-----|:--------|
| Running containers | `docker ps` |
| Hash of running containers | `docker ps -q` |
| All containers | `docker ps -a` |
| Hash of all containers | `docker ps -aq` |


### Containers: Managing

| task | command |
|:-----|:--------|
| Kill running containers | `docker kill $(docker ps -q)` |
| Remove all exited containers | `docker container prune` |
| Remove old containers | `docker ps -a | grep 'weeks ago' | awk '{print $1}' | xargs docker rm` |
| Remove all containers	 | `docker rm -f $(docker ps -qa)` |


### Save and load

| task | command |
|:-----|:--------|
| Save a image to a .tar file | `docker save -o <path to tar file> <image name>` |
| Load a .tar file | `docker load -i <path to tar file>` |
