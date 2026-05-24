# Common Kubernetes commands

## Cluster

- Check Cluster Info
```bash
kubectl cluster-info
```

- View all nodes
```bash
kubectl get nodes 
```

- Detailed info of a node
```bash
kubectl describe node <node-name>
```


## Pods

- View pods
```bash
kubectl get pods
```

- View pods in all namespaces
```bash
kubectl get pods -A
```

- Wide output
```bash
kubectl get pods -o wide
```

- Describe a pod
```
kubectl describe pod <pod-name>
```

- View pod logs
```bash
kubectl logs <pod-name>
```

- Get live pod logs
```bash
kubectl log -f <pod-name>
```

- Delete pod
```bash
kubectl delete pod <pod-name>
```


## Deployment

- View deployments
```
kubectl get deploy
```

- Apply deployment.yaml
```bash
kubectl apply -f deployment.yaml
```

- Describe deployment
```bash
kubectl describe deploy <deployment-name>
```

- Restart deployment
```bash
kubectl rollout restart deployment <deployment-name>
```

- Delete deployment
```bash
kubectl delete deploy <deployment-name>
```


## Service

- View services
```bash
kubectl get svc
```

- Describe service
```bash
kubectl describe svc <service-name>
```

- Apply service.yaml
```bash
kubectl apply -f service.yaml
```

- Delete service
```bash
kubectl delete svc <service-name>
```


## Namespace

- View namespaces
```bash
kubectl get ns
```

- Create namespace
```bash
kubectl create namespace dev
```

- Delete namespace
```bash
kubectl delete namespace dev
```