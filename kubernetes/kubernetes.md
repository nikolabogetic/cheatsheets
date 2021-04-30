# Kubernetes

```bash
kubectl version --client
kubectl.docker version --client
```

Change namespace
```
kubectl config set-context --current --namespace=my-namespace
```

Insecure kubectl
```
alias k="kubectl --insecure-skip-tls-verify"
```


```
kubectl get pods -n kube-system -o wide
```

Cluster details
```
kubectl get cs
kubectl cluster-info
```

Run test pod
```
kubectl run test1 -it --rm --image busybox -- sh
```
