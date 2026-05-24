## Kubernetes Deployment
- A pod in itself is incapable of auto-healing and auto-scaling capabilities
- Deployment helps by providing these features
- Prefer creating a pod using a deployment resource
- The deployment resource creates a replica set (Kubernetes controller) 
- A replica set controller creates the no. of replicas of the pod mentioned in the YAML file
- Helps in achieving a zero-downtime environment

## The deployment.yaml file
- Defines how the application should run inside the container
- Basic structure of such a file
```
apiVersion: apps/v1
kind: Deployment

metadata:
  name: my-app

spec:
  replicas: 2

  selector:
    matchLabels:
      app: my-app

  template:
    metadata:
      labels:
        app: my-app

    spec:
      containers:
        - name: my-container
          image: nginx
          ports:
            - containerPort: 80
```

- The YAML files work in a key: value pair format 
	```image: nginx```
- Indentation defines hierarchy
```
metadata:
	name: my-app
```
- YAML uses **spaces** not tabs
- A dash (-) means list item
```
containers:
	- name: nginx,
	  image: nginx
```

- Top level fields
- Most YAML files contain:
```
apiVersion
kind
metadata 
spec
```

1. **apiVersion**: defines what Kubernetes api version is being used

| Resource   | apiVersion           |
| ---------- | -------------------- |
| Deployment | apps/v1              |
| Service    | v1                   |
| Pod        | v1                   |
| ConfigMap  | v1                   |
| Ingress    | networking.k8s.io/v1 |

2. **kind**: defines what object you're creating

|Kind|Purpose|
|---|---|
|Pod|Single pod|
|Deployment|Manage pods|
|Service|Networking|
|ConfigMap|Store configs|
|Secret|Store sensitive data|

3. **metadata**: information about the project
```yaml
metadata:
	name: my-app
```


4. **spec**: defines the desired state
	- **replicas**: how many pod copies should run
	- **selector**: defines how deployment finds its pods
	```yaml
	selector:
	  matchLabels:
	    app: my-app
	```
	- Manage all pods having label -> app: my-app
	  
	- **template**: defines the pod blueprint
		- **template.metadata.labels**: these labels must match selector labels
		```yaml
		template:
			metadata:
				labels:
					app: my-app
		```
	
		- **template.spec**: actual pod configuration
		- This contains:
			- containers
			- volumes
			- nodeSelector
			- tolerations
			- imagePullSecrets
			- etc.
			  
		- **template.spec.container**: list of containers inside pod, a pod can have multiple containers
			- Container fields:
				- *name*: container name
				- *image*: docker image
				- *imagePullPolicy*: controls image pulling
					- *always*: pull every time(latest image)
					- *IfNotPresent*: pull only if missing on the node
					- *Never*: never pull
				- *ports*: container exposed ports