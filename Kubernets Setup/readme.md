# Kubernets Setup
## Creation of pods
### Step 1:

- Creation of pod.yaml file using commands 
```bash
$ nano pod.yaml
```

```bash
 apiVersion: v1
kind: Pod
metadata:
  name: configmap-demo-1
spec:
  containers:
  - name: demo-container
    image: nginx
    envFrom:
    - configMapRef:
       name: configmap-1
```
```bash
$ kubectl create -f pod.yaml
```

### Step 2:
- To check whether pod is runing or not
```bash
$ kubctl get pod
```

### Step 3:
```bash
$ kubectl delete pod <name>
```