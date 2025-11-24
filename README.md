Infrastructure Monitoring and Management Dashboard
1. Project Overview

This project provides an internal dashboard for monitoring and managing a Kubernetes-based infrastructure deployed on virtual machines. The system offers real-time visibility on workloads, cluster resources, configurations and events. It also includes basic operational controls and tools for creating or importing Kubernetes resources.

The focus of the work was on virtualization, deployment, resource monitoring and integration within the company’s infrastructure.

2. Functional Scope
2.1 Workload Monitoring

The dashboard provides real-time information and visual summaries (charts, counters) for:

CronJobs

Deployments

Jobs

Pods

ReplicaSets

DaemonSets

StatefulSets
<img width="240" height="784" alt="image" src="https://github.com/user-attachments/assets/95764c32-b930-4bc5-9fac-e570125b7c52" /> <img width="216" height="410" alt="image" src="https://github.com/user-attachments/assets/f2519fce-be6b-46fc-817a-069b5ee7824f" />



Workload status is presented through charts showing Running, Failed, and Pending states, along with detailed tables for each resource.
<img width="1919" height="926" alt="image" src="https://github.com/user-attachments/assets/c9a50f46-c34b-45d0-a14d-ce3b896b5fc4" />


2.2 Cluster Resources and Configuration

The system provides access to a wide set of Kubernetes components, including:

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

Each resource includes structured metadata, status, and event history.
<img width="1919" height="930" alt="image" src="https://github.com/user-attachments/assets/9674639b-f153-4f13-9d0a-a678f230dbb1" />

2.3 Resource Creation and Import

The dashboard includes a section allowing:

Creation of new Kubernetes objects directly from the interface (YAML editor).
<img width="1649" height="579" alt="image" src="https://github.com/user-attachments/assets/66f333e0-4e4c-431e-8112-a2b9b0f4ebf1" />

Importing existing YAML definitions for rapid deployment.
<img width="1662" height="277" alt="image" src="https://github.com/user-attachments/assets/a436b5d2-31ce-4c89-b39c-1623d9ecded8" />

Validation of configurations before applying them to the cluster.
<img width="1650" height="819" alt="image" src="https://github.com/user-attachments/assets/4381ead8-06dc-4983-a8cc-f64a803798eb" />

2.4 Event Notifications

The system includes an event-driven notification panel that reports:

Pod restarts or failures

Job scheduling or termination

Deployment updates

Node readiness changes

Warnings and cluster-level issues

Notifications are displayed in real time and categorized for easier troubleshooting.
<img width="470" height="463" alt="image" src="https://github.com/user-attachments/assets/3b828ed4-501b-47a4-bcd2-ff677bedf634" />

2.5 Management Operations

Basic operational actions are supported:

Start, stop or restart workloads

Inspect logs and recent events

Refresh workload status
These tools are designed to simplify daily operations for infrastructure teams.
<img width="1655" height="817" alt="image" src="https://github.com/user-attachments/assets/325419c1-836c-4a17-9b9c-de770cfe5809" />
<img width="1661" height="810" alt="image" src="https://github.com/user-attachments/assets/caec96ee-1760-4c9f-bd35-0c757ffc4635" />

3. Technical Environment
3.1 Virtualization

Deployment of the Kubernetes cluster across multiple virtual machines.

VM configuration for networking, resource allocation and cluster communication.

Ensuring stable API access for monitoring components.

3.2 Deployment and Integration

Integration of the dashboard with existing infrastructure tools.

Implementation of the data collection layer querying the Kubernetes API.

Ensuring compatibility with cluster authentication and role-based access.

3.3 Architecture Summary

Virtualized Kubernetes environment running on VMs

Monitoring layer (API queries and metric collection)

Management layer (operational actions, resource YAML handling)

Dashboard interface with workload charts, tables and notifications

4. Technologies Used

(To be customized with your exact stack.)

Kubernetes

Virtualized VM infrastructure

Internal API interaction scripts/services

Dashboard or front-end framework used for visualization

5. Contributions

Setup of the virtual machine environment supporting the Kubernetes deployment

Deployment and configuration of the monitoring dashboard

Implementation of workload views, cluster resource pages, and event notifications

Integration of resource creation/import features

Testing, validation and adjustments for internal production stability

6. Project Status

The system is fully functional for internal use, providing monitoring, cluster resource inspection, event notifications and basic operational control.
Additional improvements may be added based on future infrastructure requirements.
