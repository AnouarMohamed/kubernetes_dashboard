Infrastructure Monitoring and Management Dashboard
1. Overview

This project consists of an internal dashboard designed to monitor and manage a Kubernetes-based infrastructure deployed on virtual machines. It provides real-time visibility into workloads, cluster resources, configurations, and system events. The platform also supports operational actions, resource creation/import, and integrates with the company’s existing virtualized environment.

The main focus of the work was on virtualization, deployment, monitoring, and infrastructure integration.

2. Functional Scope
2.1 Workload Monitoring

The dashboard displays real-time information and visual summaries for:

CronJobs

Deployments

Jobs

Pods

ReplicaSets

DaemonSets

StatefulSets

These views include charts, statistical breakdowns, and detailed resource tables.

<img src="https://github.com/user-attachments/assets/95764c32-b930-4bc5-9fac-e570125b7c52" width="240" height="784"> <img src="https://github.com/user-attachments/assets/f2519fce-be6b-46fc-817a-069b5ee7824f" width="216" height="410">

Workload status is displayed with Running / Failed / Pending indicators.

<img src="https://github.com/user-attachments/assets/c9a50f46-c34b-45d0-a14d-ce3b896b5fc4" width="100%">
2.2 Cluster Resources and Configuration

The dashboard exposes a full cluster-level view, including:

ConfigMaps

Persistent Volume Claims

Secrets

Storage Classes

Nodes

Persistent Volumes

Namespaces

Network Policies

Cluster Roles

Role Bindings

Service Accounts

Custom Resource Definitions

Each resource category includes metadata, status details, and event history.

<img src="https://github.com/user-attachments/assets/9674639b-f153-4f13-9d0a-a678f230dbb1" width="100%">
2.3 Resource Creation and Import

A dedicated section allows users to manage Kubernetes objects directly from the interface.

YAML Creation
<img src="https://github.com/user-attachments/assets/66f333e0-4e4c-431e-8112-a2b9b0f4ebf1" width="100%">

YAML Import
<img src="https://github.com/user-attachments/assets/a436b5d2-31ce-4c89-b39c-1623d9ecded8" width="100%">

Configuration Validation
<img src="https://github.com/user-attachments/assets/4381ead8-06dc-4983-a8cc-f64a803798eb" width="100%">

2.4 Event Notifications

A real-time event panel reports:

Pod failures or restarts

Job scheduling and termination

Deployment updates

Node state changes

Cluster warnings and errors

Notifications are streamed from the cluster and organized by severity and type.

<img src="https://github.com/user-attachments/assets/3b828ed4-501b-47a4-bcd2-ff677bedf634" width="35%">
2.5 Management Operations

The system supports a set of operational tasks, including:

Starting and stopping workloads

Inspecting logs

Viewing recent events

Refreshing workload status

These tools streamline day-to-day cluster operations.

<img src="https://github.com/user-attachments/assets/325419c1-836c-4a17-9b9c-de770cfe5809" width="100%"> <img src="https://github.com/user-attachments/assets/caec96ee-1760-4c9f-bd35-0c757ffc4635" width="100%">
3. Technical Environment
3.1 Virtualization

Deployment of Kubernetes nodes across multiple virtual machines

VM-level networking and resource allocation

Ensuring reliable API communication and service availability

3.2 Deployment and Integration

Integration of the dashboard with the existing infrastructure

Implementation of the data layer communicating with the Kubernetes API

Support for authentication and role-based access controls

3.3 Architecture Summary

Virtualized Kubernetes cluster running on VMs

Monitoring layer for metric and resource collection

Management layer for YAML operations and workload control

Dashboard frontend with charts, resource tables and notifications

4. Technologies Used

(Adjust according to your exact stack.)

Kubernetes

Virtualized VM environment

Internal API services

Dashboard frontend technology

Supporting automation tools

5. Contributions

During this project, the following contributions were completed:

Preparing and managing the virtual machine environment for the cluster

Deploying and configuring the dashboard

Implementing monitoring views for workloads and cluster resources

Adding resource creation/import features

Building the event notification system

Testing, debugging, and optimizing the deployment

6. Project Status

The dashboard is fully operational and used internally for monitoring, inspection, event handling, and basic cluster management. Future improvements may extend functionality based on infrastructure needs.
