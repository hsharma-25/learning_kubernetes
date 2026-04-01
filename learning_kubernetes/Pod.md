## Pod
- Lowest level of deployment in Kubernetes is pod
- A pod can be a single or multiple containers
- Unlike the command line in docker, all the information of a pod is put inside a **YAML** file
- Why to deploy container as a pod and why can't we directly use the container
- Putting multiple containers inside a pod allows for shared network and shared storage
- Kubeproxy assigns a **cluster ip** address to a pod for communication