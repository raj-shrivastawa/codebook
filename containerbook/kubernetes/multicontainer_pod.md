1. Init containers.
```bash
kubectl explain pod.spec.initContainers
```
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: testcreds
spec:
  containers:
    - image:
      name:
  initContainers:
    - image:
      name:
```
