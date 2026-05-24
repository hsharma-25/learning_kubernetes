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

## The service.yaml file
- Basic structure:
```yaml
apiVersion: v1
kind: Service

metadata:
  name: my-service

spec:
  selector:
    app: my-app

  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080

  type: ClusterIP
```

1. **apiVersion**
	- define K8s api version
	- for service usually, "v1" is used
	  
2. **kind**
	- tells K8s that this resource is a service
	  
3. **metadata**
	- information about the Service
	- usually the name you want to give to the service
	- common fields: *name*, *namespace*, *labels*
	  
4. **spec**
	- main configuration section
	- **spec.selector**
		- service forwards traffic to pods matching these labels
	  
	- **spec.ports**
		- networking ports configuration
		- *spec.ports.protocol*: usually TCP
		- *spec.ports.port*: the port exposed by the service
		- *spec.ports.targetPort*: port inside container/pod
		- traffic flow: Client -> Service: 80 -> Pod: 8080
	
	- **spec.type**
		- determines how service is exposed
		- can be: ClusterIP, NodePort, LoadBalancer