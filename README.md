# Kubernetes Dashboard

A lightweight, extensible Kubernetes dashboard providing a web-based interface for visualizing and interacting with Kubernetes cluster resources.  
This project demonstrates containerized application design, Kubernetes-native deployment, and secure cluster access using RBAC.

The dashboard is designed to run both locally (Docker / Docker Compose) and inside a Kubernetes cluster using in-cluster configuration.

---

## Table of Contents

- Project Overview
- Features
- Use Cases
- Repository Structure
- Technology Stack
- Prerequisites
- Installation
  - Local (Docker)
  - Local (Docker Compose)
  - Kubernetes Deployment
- Configuration
- API Documentation
- Kubernetes Production Setup
  - Namespaces
  - Service Accounts
  - RBAC
  - Security Considerations
- Architecture
- Development Guide
- Testing
- Deployment Strategy
- Contributing
- License

---

## Project Overview

This project is a custom Kubernetes dashboard developed to demonstrate practical DevOps and cloud-native concepts, including:

- Kubernetes API integration
- Containerized application workflows
- Infrastructure-as-code using Kubernetes manifests
- Secure access to cluster resources

It is intentionally minimal and modular, making it suitable for learning, extension, or adaptation to production-grade environments.

---

## Features

- Web-based dashboard interface
- Real-time visualization of Kubernetes resources
- Backend communication with Kubernetes API
- Dockerized application environment
- Kubernetes-ready deployment manifests
- RBAC-based access control
- Easily extensible backend architecture

---

## Use Cases

- Learning Kubernetes API interactions
- DevOps portfolio project
- Internal cluster visualization tool
- Base template for custom Kubernetes management UIs
- Academic demonstration of cloud-native systems

---

## Repository Structure

```text
.
├── app/                      # Application source code (backend / UI)
│   ├── main.py               # Application entry point
│   ├── routes/               # API routes (if applicable)
│   └── services/             # Kubernetes client logic
├── k8s/                      # Kubernetes manifests
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── rbac.yaml
│   └── serviceaccount.yaml
├── Dockerfile                # Docker image definition
├── docker-compose.yml        # Local development orchestration
├── requirements.txt          # Python dependencies
└── README.md                 # Documentation
````

---

## Technology Stack

* Backend: Python (Flask or FastAPI style architecture)
* Containerization: Docker
* Orchestration: Kubernetes
* API Access: Kubernetes Python Client
* Configuration: Environment variables and manifests

---

## Prerequisites

Ensure the following are installed:

* Docker
* Docker Compose
* Kubernetes cluster (Minikube, Kind, K3s, or cloud provider)
* kubectl
* Python 3.9+ (for local development)

---

## Installation

### Local Installation (Docker)

Build the image:

```sh
docker build -t kubernetes-dashboard .
```

Run the container:

```sh
docker run -p 8080:8080 kubernetes-dashboard
```

Access the dashboard:

```
http://localhost:8080
```

---

### Local Installation (Docker Compose)

```sh
docker-compose up --build
```

This mode is recommended for development and debugging.

---

### Kubernetes Deployment

Deploy all Kubernetes resources:

```sh
kubectl apply -f k8s/
```

Verify deployment:

```sh
kubectl get pods
kubectl get services
```

Expose locally:

```sh
kubectl port-forward svc/kubernetes-dashboard 8443:8443
```

Access:

```
https://localhost:8443
```

---

## Configuration

Configuration is handled via environment variables.

Example:

```env
DASHBOARD_PORT=8080
KUBERNETES_NAMESPACE=default
```

Configuration sources:

* Docker environment variables
* docker-compose.yml
* Kubernetes Deployment environment section

---

## API Documentation

The backend exposes REST endpoints to retrieve Kubernetes data.

Example endpoints (typical structure):

| Method | Endpoint         | Description              |
| ------ | ---------------- | ------------------------ |
| GET    | /api/health      | Application health check |
| GET    | /api/nodes       | List cluster nodes       |
| GET    | /api/pods        | List pods                |
| GET    | /api/services    | List services            |
| GET    | /api/deployments | List deployments         |

All endpoints communicate with the Kubernetes API using in-cluster credentials or kubeconfig.

---

## Kubernetes Production Setup

### Namespace

Recommended to deploy in a dedicated namespace:

```sh
kubectl create namespace dashboard
```

---

### Service Account

The dashboard runs using a dedicated ServiceAccount:

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: dashboard-sa
  namespace: dashboard
```

---

### RBAC

Minimal RBAC permissions example:

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: dashboard-reader
rules:
- apiGroups: [""]
  resources: ["pods", "services", "nodes"]
  verbs: ["get", "list", "watch"]
```

Binding:

```yaml
kind: ClusterRoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: dashboard-binding
subjects:
- kind: ServiceAccount
  name: dashboard-sa
  namespace: dashboard
roleRef:
  kind: ClusterRole
  name: dashboard-reader
  apiGroup: rbac.authorization.k8s.io
```

---

### Security Considerations

* Use least-privilege RBAC rules
* Avoid ClusterAdmin in production
* Restrict dashboard exposure (Ingress with auth)
* Use HTTPS termination
* Run container as non-root

---

## Architecture

High-level flow:

1. User accesses web UI
2. Backend receives request
3. Backend queries Kubernetes API
4. Data is returned and rendered in UI

Deployment modes:

* Local Docker (development)
* In-cluster Kubernetes (production)

---

## Development Guide

Install dependencies:

```sh
pip install -r requirements.txt
```

Run locally:

```sh
python app/main.py
```

Code quality:

```sh
black .
flake8 .
```

---

## Testing

Basic testing strategy:

* Unit tests for API routes
* Mocked Kubernetes API responses
* Integration testing using Minikube

Run tests:

```sh
pytest
```

---

## Deployment Strategy

Recommended progression:

1. Local Docker testing
2. Docker Compose integration
3. Minikube or Kind deployment
4. Production Kubernetes cluster

Supports CI/CD pipelines for automated builds and deployments.

---

## Contributing

Contributions are welcome.

Contribution workflow:

1. Fork the repository
2. Create a feature branch
3. Commit changes with clear messages
4. Submit a pull request

Please ensure:

* Code is formatted
* Tests pass
* Documentation is updated

---
