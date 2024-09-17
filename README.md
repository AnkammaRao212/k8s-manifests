# k8s-manifests
=========================

Kubernetes is an open-source platform designed to automate deploying, scaling, and managing 
containerized applications. It helps manage clusters of containers and enables efficient 
orchestration, allowing easier deployment, scaling, and management of applications in a flexible 
and scalable manner.

**Kubernetes architecture :**

![image](https://github.com/user-attachments/assets/65e4b73a-e451-44fd-8760-6d03bff1cf88)



Kubernetes Control Plane Components
The control plane’s components make global decisions about the cluster, as well as detecting and responding to cluster events. Kubernetes relies on several administrative services running on the control plane. These services manage aspects, such as cluster component communication, workload scheduling, and cluster state persistence.

API Server (kube-apiserver)
API server exposes the Kubernetes API.
Entry point for REST/kubectl — It is the front end for the Kubernetes control plane.
It tracks the state of all cluster components and managing the interaction between them.
It is designed to scale horizontally.
It consumes YAML/JSON manifest files.
It validates and processes the requests made via API.

etcd (key-value store)
It is a consistent, distributed, and highly-available key value store.
It is stateful, persistent storage that stores all of Kubernetes cluster data (cluster state and config).
It is the source of truth for the cluster.
It can be part of the control plane, or, it can be configured externally.
Scheduler (kube-scheduler)
It schedules pods to worker nodes.
It watches api-server for newly created Pods with no assigned node, and selects a healthy node for them to run on.
If there are no suitable nodes, the pods are put in a pending state until such a healthy node appears.
It watches API Server for new work tasks.
Factors taken into account for scheduling decisions include:

Individual and collective resource requirements.
Hardware/software/policy constraints.
Affinity and anti-affinity specifications.
Data locality.
Inter-workload interference.
Deadlines and taints.
Controller Manager (kube-controller-manager)
It watches the desired state of the objects it manages and watches their current state through the API server.
It takes corrective steps to make sure that the current state is the same as the desired state.
It is controller of controllers.
It runs controller processes. Logically, each controller is a separate process, but to reduce complexity, they are all compiled into a single binary and run in a single process.
Some types of controllers are:

Node controller: Responsible for noticing and responding when nodes go down.
Job controller: Watches for Job objects that represent one-off tasks, then creates Pods to run those tasks to completion.
Endpoints controller: Populates the Endpoints object (that is, joins Services & Pods).
Service Account & Token controllers: Create default accounts and API access tokens for new namespaces.

