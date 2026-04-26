# K8s Deployment Demo

A Kubernetes demonstration project showing MongoDB deployment with Mongo Express UI.

## Overview

This project contains Kubernetes manifests for deploying:

- **MongoDB**: NoSQL database deployment
- **Mongo Express**: Web-based MongoDB admin interface
- **ConfigMaps**: Configuration management for application settings
- **Secrets**: Sensitive data (credentials) management

## Project Structure

```
.
├── mongo.yaml              # MongoDB deployment manifest
├── mongo-express.yaml      # Mongo Express deployment manifest
├── mongo-secret.yaml       # Kubernetes secret for credentials
├── mongo-configmap.yaml    # Kubernetes configmap for configuration
└── README.md              # This file
```

## Prerequisites

- Kubernetes cluster (minikube, Docker Desktop K8s, or cloud K8s)
- kubectl CLI configured to access your cluster
- Basic understanding of Kubernetes concepts

## Getting Started

### Deploy to Kubernetes

```bash
# Apply all manifests
kubectl apply -f .

# Verify deployments
kubectl get deployments
kubectl get pods
kubectl get services
```

### Access Mongo Express

```bash
# Port forward to access the UI locally
kubectl port-forward svc/mongo-express 8081:8081

# Open in browser
open http://localhost:8081
```

## Configuration

- **Secrets**: Database credentials are managed via `mongo-secret.yaml`
- **ConfigMap**: Application configurations are in `mongo-configmap.yaml`

## Cleanup

```bash
# Remove all resources
kubectl delete -f .
```

## Next Steps

- Add services and ingress configurations
- Implement persistent volumes for data persistence
- Add health checks and resource limits
- Configure resource quotas and network policies
