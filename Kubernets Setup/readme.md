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


# Imperative

- Creation of pods
```bash
$ kubectl run <name> --image=nginx:alpine --restart=Never
```

- Creation of nginx and expose to port 8080

```bash
$ kubectl run nginx --image=nginx:alpine --port=8080 --restart=Never
```