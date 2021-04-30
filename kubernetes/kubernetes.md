# Kubernetes

```bash
kubectl version --client
kubectl version --short
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
kubectl get cs (deprecated)
kubectl cluster-info
kubectl config view
```

Run test pod
```
kubectl run test1 -it --rm --image busybox -- sh
```



Minikube on Mac
```
brew install hyperkit
brew install minikube
minikube start --driver=hyperkit

minikube status
```
```
kubectl get nodes | pods | services | deployments | secrets [--watch] [-n <namespace>]


kubectl create deployment NAME --image=image [--dry-run]

kubectl delete -f <file>
```

Helm
```
helm version

helm repo add stable https://kubernetes-charts.storage.googleapis.com

helm install registry stable/docker-registry \
  --version 1.9.4 \
  --namespace kube-system \
  --set service.type=NodePort \
  --set service.nodePort=31500
```

```
k get pod -w
# Watch

k run test1 -it --rm --image praqma/network-multitool -- /bin/sh

k -n kube-system rollout restart deployment coredns

kubectl expose deployment myapp-deployment --type=ClusterIP --name=myapp-svc
```

```
cat server.csr | base64 | tr -d '\n'
```

```
kubectl create ns <namespace>

kubectl config set-context --current --namespace=<namespace>
```

```
kubectl create secret generic hello.world.com --from-file=tls.crt=hello.world.com.crt --from-file=tls.key=hello.world.com.key
```

