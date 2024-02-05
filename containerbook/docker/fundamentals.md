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
### docker volume(persistent)
```bash
docker run -ti --name busybox -v /tmp/dvol:/opt busybox
```
* Here `/tmp/dvol` is host dir and `/opt` is path inside container.
* If pod will be killed/removed data will be avaialble on host path.
