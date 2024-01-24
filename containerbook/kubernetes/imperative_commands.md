1. create a namespace and run container with image nginx and name nginx.  
```bash
kubectl create ns mynamespace
kubectl run nginx --image=nginx -n mynamespace
```
