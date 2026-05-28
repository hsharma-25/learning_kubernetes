# Kubernetes Ingress

## Limitations with service
- Service wasn't able to provide various enterprise-level capabilities 
- Enterprise and TLS load-balancing
- Cloud provider would charge for each LoadBalancer service leading to high costs

## What is Ingress
- Ingress acts as a **smart router** for incoming traffic
- Supports **host based routing**
- Supports **path based routing**
- Handles **TLS/SSL termination** etc.

## Ingress Controller
- Implements the ingress rules in K8s
- Rules are defined as a YAML configuration
- Ingress controller reads the rules and routes traffic accordingly

## Popular Ingress Controllers
- NGINX
- Traefik
- HAProxy etc.

