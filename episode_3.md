# Episode 3 - Deploying Apps

- `kubectl create deployment hello-go --image=geerlingguy/kube101-go:1.0.0` - create deployment from image
- `kubectl get pod -l app=hello-go` -l (label) app=label
- `kubectl describe pod -l app=hello-go` - gives some events to start debugging
- `kubectl create secret docker-registry <secret --docker-username=<username> --docker-password=<password> --docker-email=<email>` - create kubernetes secret
- `kubectl delete secret <secret>` - delete kubernetes secret
- `kubectl get secrets` - show kubernetes secrets
