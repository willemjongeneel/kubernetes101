# Episode 1 - Hello, Kubernetes!

- masternode - etcd
- workernode - pods
- workernode - pods

kubernetes: software defined cluster

### kubernetes tools
- kubeadm - tool to setup k8s cluster
- k3s (Rancher) - lightweight kubernetes 
- kind - kubernetes in docker (lets you build clusters in a development environment)
- minikube - to develop with kubernetes, very user friendly
- openshift - for running in production
- k0s - very lightweight, distributes as one binary

### steps to install test cluster 
1. `brew install minikube` - installs minikube
2. `brew install kubectl` - installs kubectl
3. `minikube start` - starts minikube cluster

### kubectl commands 
- `kubectl get nodes` - shows available kubernetes nodes
- `kubectl create deployment hello-k8s --image=geerlingguy/kube101:intro` - deploys image to the kubernetes cluster and names the deployment hello-k8s
- `kubectl expose deployment hello-k8s --type=NodePort --port=80` - By default everything deployed inside your kubernetes cluster is unreachable from the host server/computer. You need to expose the deployment as a service to be able to reach it. When you expose it, it creates a service.
- `kubectl get services hello-k8s` - Returns the port under which the service is accessible from the host server.
- `minikube ip` - shows the minikube ip
- `minikube service hello-k8s` - opens the service in the browser
- `minikube halt` - stops the minikube cluster
- `minikube delete` - deletes the minikube cluster

### kubernetes documentation 
- https://kubernetes.io/docs/home/
- there is a kubernetes slack 

