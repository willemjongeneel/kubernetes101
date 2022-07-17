# Episode 1 - Hello, Kubernetes!

- masternode - etcd
- workernode - pods
- workernode - pods

kubernetes: software defined cluster

kubernetes tools
- kubeadm - tool to setup k8s cluster
- k3s (Rancher) - lightweight kubernetes 
- kind - kubernetes in docker (lets you build clusters in a development environment)
- minikube - to develop with kubernetes, very user friendly
- openshift - for running in production
- k0s - very lightweight, distributes as one binary

steps to install test cluster 
1. `brew install minikube` - installs minikube
2. `brew install kubectl` - installs kubectl
3. `minikube start` - starts minikube cluster
