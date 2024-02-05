### Port mapping
Map host port with container port.  
```bash
docker run -d --name redis -p 6379:6379 redis
```
### Create network and attach container to the network.  
* If container exist in the same network then only it will be able to communicate. If no network provided container will use default network.
```bash
docker network ls
docker network create devcsm --driver=bridge
docker run -d --name nginx --network devcsm nginx
docker run -ti --network devcsm busybox sh
ping 172.18.0.2 # nginx ip
```
* If no network provided it will use bridge network docker0(172.17.0.1)
```bash
docker inspect mynetwork # Inspect network
```
### docker volume(persistent)
```bash
docker run -ti --name busybox -v /tmp/dvol:/opt busybox
```
* Here `/tmp/dvol` is host dir and `/opt` is path inside container.
* If pod will be killed/removed data will be avaialble on host path.
### Basic commands containers
```bash
docker ps
docker ps -a # show stopped containers as well
docker stop <container_name>
docker rm <container_name>
```
### Basic commands images
```bash
docker images
docker rmi <image_name> # remove image
docker pull <image> # only pull locally
docker run ubuntu sleep 5 # run sleep 5 when container starts
```
### Accessing container
```bash
docker exec nginx cat /etc/hosts
docker exec -ti nginx sh
```
### Attach/detach 
```bash
docker run -d --name mynginx nginx
docker attach <container>
```
### Inspecting container
```bash
docker inspect mynginx
```
### Monitoring/Logging
```bash
docker logs mynginx
docker logs --tail 50 mynginx
docker logs mynginx -f
```
### Environment variable in docker container
```bash
docker run -e APP_COLOR=green simple-webapp-color
```
### ENTRYPOINT VS CMD
* CMD will be appended with ENTRYPOINT for an example ENTRYPOINT "sleep" and CMD "5"
### File system
* /var/lib/docker
  1. aufs
  2. containers
  3. image
  4. volumes
### Links
