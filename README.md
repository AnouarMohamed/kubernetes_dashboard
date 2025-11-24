# Infrastructure Monitoring and Management Dashboard

## Table of Contents
1. [Overview](#overview)  
2. [Functional Scope](#functional-scope)  
   - [Workload Monitoring](#workload-monitoring)  
   - [Cluster Resources and Configuration](#cluster-resources-and-configuration)  
   - [Resource Creation and Import](#resource-creation-and-import)  
   - [Event Notifications](#event-notifications)  
   - [Management Operations](#management-operations)  
3. [Technical Environment](#technical-environment)  
   - [Virtualization](#virtualization)  
   - [Deployment and Integration](#deployment-and-integration)  
   - [Architecture Summary](#architecture-summary)  
4. [Technologies Used](#technologies-used)  
5. [Installation and Setup](#installation-and-setup)  
6. [Usage](#usage)  
7. [Contributions](#contributions)  
8. [Project Status](#project-status)  
9. [Screenshots](#screenshots)  
10. [Architecture Diagram](#architecture-diagram)

---

## Overview

This project provides an internal dashboard for real-time monitoring and management of a Kubernetes-based infrastructure deployed on virtual machines.  
It enables full visibility into workloads, cluster resources, configurations, and system events, while supporting operational actions, resource creation, and import workflows.

Focus areas:

- Virtualization and cluster setup  
- Kubernetes integration  
- Monitoring and metric visualization  
- Infrastructure-level operations  

---

## Functional Scope

### Workload Monitoring

Real-time monitoring for Kubernetes workloads:

- CronJobs  
- Deployments  
- Jobs  
- Pods  
- ReplicaSets  
- DaemonSets  
- StatefulSets  

Features:

- Status indicators (Running / Pending / Failed)  
- Charts and statistical summaries  
- Filterable and sortable tables  

Example screenshot:  
![Workload Monitoring](https://github.com/user-attachments/assets/c9a50f46-c34b-45d0-a14d-ce3b896b5fc4)

---

### Cluster Resources and Configuration

Cluster-wide visibility into:

- ConfigMaps  
- Persistent Volume Claims  
- Secrets  
- Storage Classes  
- Nodes  
- Persistent Volumes  
- Namespaces  
- Network Policies  
- Cluster Roles / Role Bindings  
- Service Accounts  
- Custom Resource Definitions  

Each resource shows metadata, status, and event logs.

Example screenshot:  
![Cluster Resources](https://github.com/user-attachments/assets/9674639b-f153-4f13-9d0a-a678f230dbb1)

---

### Resource Creation and Import

Features:

- YAML creation through an integrated editor  
- YAML import and validation  
- Error reporting and debugging  

Screenshots:

- YAML Creation  
![YAML Creation](https://github.com/user-attachments/assets/66f333e0-4e4c-431e-8112-a2b9b0f4ebf1)  
- YAML Import  
![YAML Import](https://github.com/user-attachments/assets/a436b5d2-31ce-4c89-b39c-1623d9ecded8)  
- Configuration Validation  
![Validation](https://github.com/user-attachments/assets/4381ead8-06dc-4983-a8cc-f64a803798eb)

---

### Event Notifications

Real-time events include:

- Pod failures and restarts  
- Job scheduling and termination  
- Deployment updates  
- Node state changes  
- Cluster warnings and errors  

Events are streamed and organized by type and severity.

Example screenshot:  
![Event Notifications](https://github.com/user-attachments/assets/3b828ed4-501b-47a4-bcd2-ff677bedf634)

---

### Management Operations

Operational tasks:

- Start/stop workloads  
- View logs  
- Inspect recent events  
- Refresh resource status  

Screenshots:  
![Management 1](https://github.com/user-attachments/assets/325419c1-836c-4a17-9b9c-de770cfe5809)  
![Management 2](https://github.com/user-attachments/assets/caec96ee-1760-4c9f-bd35-0c757ffc4635)

---

## Technical Environment

### Virtualization

- Kubernetes nodes deployed across multiple VMs  
- Network configuration and resource allocation  
- API stability and service reliability  

### Deployment and Integration

- Integration with existing infrastructure  
- Backend services communicating with Kubernetes API  
- Authentication and role-based access control  

### Architecture Summary

- Virtualized Kubernetes cluster  
- Monitoring and metrics collection layer  
- Management layer for YAML and operational tasks  
- Dashboard frontend with charts, tables, and notifications  

---

## Technologies Used

- Kubernetes  
- Virtualized VM environment  
- Internal API services  
- Dashboard frontend technology  
- Automation and deployment tools  

---

## Installation and Setup

```bash
# Clone the repository
git clone <repository-url>
cd <project-directory>

# Backend installation
cd backend
npm install   # or pip install -r requirements.txt

# Frontend installation
cd ../frontend
npm install

# Configure environment
cp .env.example .env
# Modify .env with API endpoints and credentials
Requirements:

Kubernetes cluster reachable

Proper VM networking and resource allocation

Service account permissions configured

Usage

Login to the dashboard.

Select a namespace or operate cluster-wide.

Explore workloads, logs, and real-time events.

Create or import YAML configurations.

Use management tools for operational tasks.

Contributions

Preparing and managing VM infrastructure for Kubernetes

Deploying dashboard and backend services

Implementing monitoring views and metrics

Adding resource creation/import module

Building event notification system

Debugging, testing, and optimizing deployment

Project Status

The dashboard is fully operational internally for:

Workload monitoring

Cluster resource inspection

Event management

Basic operational tasks

Future improvements may include advanced analytics, alerting, and automated workflows.


Architecture Diagram
+------------------------------------------------------+
|                 Virtualized Infrastructure           |
|                                                      |
|  +--------------------+   +------------------------+ |
|  |    VM Node 1       |   |      VM Node N        | |
|  | (Worker / Master)  |   |  (Worker / Master)    | |
|  +---------+----------+   +-----------+------------+ |
|            |                          |              |
+------------|--------------------------|--------------+
             |                          |
             v                          v
      +------------------------------------------+
      |            Kubernetes Cluster            |
      |  API Server, Scheduler, Controller, etc.|
      +------------------------------------------+
                       |
                       v
      +------------------------------------------+
      |         Internal API Service Layer       |
      |  - Resource queries                      |
      |  - Event streaming                       |
      |  - Auth and RBAC                         |
      +------------------------------------------+
                       |
                       v
      +------------------------------------------+
      |        Monitoring & Management UI        |
      |  - Workload dashboards                   |
      |  - Resource explorer                     |
      |  - YAML creation/import                  |
      |  - Notifications                         |
      +------------------------------------------+
