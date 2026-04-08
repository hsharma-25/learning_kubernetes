## Kubernetes Service
- When there's no service in place:
	- After auto healing, pods get assigned new IPs and become inaccessible by other users 
	- No load balancing
- Service offers:
	- Load balancing
	- Service discovery using **labels and selectors**
	- Expose the application outside the Kubernetes cluster

## Types of Service
1. Cluster IP: default, application can be accessed only inside the Kubernetes cluster
2. Nodeport:  users with access to worker nodes' IP address can access
3. Load balancer: expose application to the world