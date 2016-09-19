Docker Cheat Sheet
===============

* [Containers](#user-content-containers)
  * [Monitor](#user-content-containers-monitor)
* [Save & Load](#user-content-save-and-load)


## Containers
Monitor containers

### Containers: Monitor

| task | command |
|:-----|:--------|
| Running containers | `docker ps` |
| Hash of running containers | `docker ps -q` |
| All containers | `docker ps -a` |
| Hash of all containers | `docker ps -aq` |


### Save and load

| task | command |
|:-----|:--------|
| Save a image to a .tar file | `docker save -o <path to tar file> <image name>` |
| Load a .tar file | `docker load -i <path to tar file>` |
