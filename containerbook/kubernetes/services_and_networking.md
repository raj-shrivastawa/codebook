```bash
kubectl get svc
kubectl get svc -o yaml
kubectl get ep # To check how many endpoints attached to service
kubectl get ep myservice# To check how many endpoints attached to service
kubectl get deploy
kubectl get deploy <deployment_name> -o yaml
```

```yaml
apiVersion: v1
kind: Service
metadata:
  name:
  namespace: default
spec:
  ports:
  - nodePort:
    port:
    targetPort:
  selector:
    name:
  type:
```
```bash
kubectl apply -f service-def.yaml
```
