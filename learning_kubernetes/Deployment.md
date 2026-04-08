## Kubernetes Deployment
- A pod in itself is incapable of auto-healing and auto-scaling capabilities
- Deployment helps by providing these features
- Prefer creating a pod using a deployment resource
- The deployment resource creates a replica set (Kubernetes controller) 
- A replica set controller creates the no. of replicas of the pod mentioned in the YAML file
- Helps in achieving a zero-downtime environment