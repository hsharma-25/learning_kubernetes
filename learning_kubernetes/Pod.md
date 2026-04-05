## Pod
- Lowest level of deployment in Kubernetes is pod
- A pod can be a single or multiple containers
- Unlike the command line in docker, all the information of a pod is put inside a **YAML** file
- Putting multiple containers inside a pod allows for shared network and shared storage
- Kubeproxy assigns a **cluster ip** address to a pod for communication
- Access the container using the cluster_ip address
- **kubectl** is the command line interface for Kubernetes

Use **describe** to get complete details of your pod
```bash
kubectl describe pod <pod_name>
```
Use **logs** to verify logs of your pod
```bash
kubectl logs <pod_name>
```
