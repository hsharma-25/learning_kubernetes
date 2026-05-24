# Namespace in Kubernetes

## Purpose of Namespaces

- Logically divide a single K8s cluster into multiple virtual clusters
- Just like a building is divided into rooms
- Resources exist on the same physical cluster but,
- Namespace helps to isolate and organize resources
- All namespaces still share:
	- the master/control plane
	- same worker nodes
	- same networking infrastructure
- Help in limiting resource usage

## Default K8s Namespaces

1. **default**
	- The namespace where resources if you don't specify one

2. **kube-system**
	- Contains K8s internal components
	- Like: CoreDNS, kube-proxy, metrics server

3. **kube-public**
	- Publicly readable resources
	- Rarely used

4. **kube-node-lease**
	- Used internally for node heartbeat information
