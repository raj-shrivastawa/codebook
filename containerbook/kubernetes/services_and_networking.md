```bash
kubectl get svc
kubectl get svc -o yaml
kubectl get ep # To check how many endpoints attached to service
kubectl get ep myservice# To check how many endpoints attached to service
kubectl get deploy
kubectl get deploy <deployment_name> -o yaml
```

### Service
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

### Network Policy  
```bash
kubectl get networkpolicy
```
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: internal-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      name: internal
  policyTypes:
  - Egress
  - Ingress
  ingress:
    - {}
  egress:
  - to:
    - podSelector:
        matchLabels:
          name: mysql
    ports:
    - protocol: TCP
      port: 3306

  - to:
    - podSelector:
        matchLabels:
          name: payroll
    ports:
    - protocol: TCP
      port: 8080
```

### Ingress
```bash
kubectl get ingress -A # To get ingress resource
```
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: 
  namespace: 
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
    nginx.ingress.kubernetes.io/ssl-redirect: "false"
spec:
  rules:
  - http:
      paths:
      - path: /pay
        pathType: Prefix
        backend:
          service:
           name: pay-service
           port:
            number: 8282
```
