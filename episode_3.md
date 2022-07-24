# Episode 3 - Deploying Apps

- `kubectl create deployment hello-go --image=geerlingguy/kube101-go:1.0.0` - create deployment from image
- `kubectl get pod -l app=hello-go` -l (label) app=label
- `kubectl describe pod -l app=hello-go` - gives some events to start debugging
- `kubectl create secret docker-registry <secret> --docker-username=<username> --docker-password=<password> --docker-email=<email>` - create kubernetes secret
- `kubectl delete secret <secret>` - delete kubernetes secret
- `kubectl get secrets` - show kubernetes secrets

### add secret to deployement
- `kubectl edit deployment hello-go`
- add '-name: regcred' under template[spec][imagePullSecrets]
- if you use different namespaces, you will need a separate pull secret for every namespace

### expose application
- `kubectl expose deployment hello-go --port=80 --target-port=8180 --type=NodePort`
- `minikube ip` - get minikube ip, use the ip when connecting to the app from the browser
- `kubectl get service hello-go` - gets node ip and port, use the port when connecting to the app from the browser

### create multiple replica's of a deployment for HA / redundancy
- `kubectl edit deployment hello-go` - edit replicas
- after running kubectl edit, the changes will be applied automatically after saving the file

### show logs
- `kubectl logs -f -l app=hello-go --prefix=true` - like tail -f for the logs, --prefix=true shows the pod that is logging the requests
