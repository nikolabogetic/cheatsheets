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



Kubernetes Commands
```
brew install hyperkit
brew install minikube
minikube start --driver=hyperkit

minikube status

kubectl get nodes | pods | services | deployments | secrets [--watch] [-n <namespace>]


kubectl create deployment NAME --image=image [--dry-run]

kubectl delete -f <file>
```
Kubectl is the main kubernetes client
```
kubectl version --short
kubectl get componentstatus
kubectl cluster-info
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

k run test1 -it --rm --image praqma/network-multitool -- /bin/bash

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
