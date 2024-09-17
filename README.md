# k8s-manifests
=========================

Kubernetes is an open-source platform designed to automate deploying, scaling, and managing 
containerized applications. It helps manage clusters of containers and enables efficient 
orchestration, allowing easier deployment, scaling, and management of applications in a flexible 
and scalable manner.

**Kubernetes architecture :**

![image](https://github.com/user-attachments/assets/65e4b73a-e451-44fd-8760-6d03bff1cf88)



Kubernetes follows a master-slave architecture consisting of various components that 
collaborate to manage and control containerized applications within a cluster. The master node 
coordinates and controls the overall state of the cluster, while worker nodes execute and manage 
the containers based on instructions from the master. This architecture provides flexibility, 
scalability, and resilience to handle diverse workloads in a distributed computing environment.
**Master Node**: Kubernetes master is responsible for managing the entire cluster, 
coordinates all activities inside the cluster, and communicates with the worker nodes to 
keep the Kubernetes and your application running. This is the entry point of all 
administrative tasks. When we install Kubernetes on our system we have four primary 
components of Kubernetes Master that will get installed.
API Server(kube api): Acts as the entry point for all administrative tasks and 
interactions within the cluster. It validates and processes requests and 
communicates with the etcd database to store configuration data. We can interact If 
we want to create, delete, update or display in Kubernetes object it has to go 
through this API server. We can interact with these APIs using a tool called kubectl.
Scheduler: Responsible for assigning workloads (containers) to nodes based on 
resource requirements, constraints, and other policies.
Controller Manager: Monitors the cluster state and responds to changes, ensuring 
that the desired state matches the actual state of the cluster. It includes various 
controllers like node controller, replication controller, and endpoints controller.
Node Controller: Manages various aspects related to nodes within the cluster. It monitors 
the nodes' health and detects node failures or changes in node status. If a node becomes 
unhealthy or goes offline, the Node Controller takes necessary actions, such as marking it 
as unhealthy and rescheduling affected pods to healthy nodes.
Replication Controller: Maintains the desired number of pod replicas specified by users or 
applications. It ensures that the requested number of pods is always running by creating 
or deleting pods as needed. If a pod fails or is removed, the Replication Controller creates 
new pods to maintain the desired state.
Endpoints Controller: Populates the Endpoints object, which links services to pods. It 
dynamically updates the Endpoints object as pods are created, deleted, or modified. This 
allows services to properly route traffic to the correct pods based on labels and selectors.
etcd: A distributed key-value database .The Cluster State Changes get stored in the 
etcd. It acts as the Cluster brain because it tells the Scheduler and other processes 
about which resources are available and about cluster state changes.
Worker Node: Kubernetes Worker node contains all the necessary services to manage the 
networking between the containers, communicate with the master node, and assign 
resources to the containers scheduled.
Kubelet: Agent running on each node, responsible for communicating with the 
master node. It manages the containers, ensuring they are running as expected by 
○
○
○
○
○
interacting with the container runtime. It gets the pod specifications through the API 
server and executes the container associated with the pods and ensures that the 
containers described in the pods are running and healthy.
Container Runtime Engine(CRE): Software responsible for running containers. 
Kubernetes supports various runtimes like Docker, containerd, and others.
Pods : A pod is a group of containers that are deployed together on the same host. 
With the help of pods, we can deploy multiple dependent containers together so it 
acts as a wrapper around these containers so we can interact and manage these 
containers primarily through pods.
Docker is the containerization platform that is used to package your application and 
all its dependencies together in the form of containers to make sure that your 
application works seamlessly in any environment which can be development or test 
or production. Docker is a tool designed to make it easier to create, deploy, and run 
applications by using containers. 
Kube Proxy: Kube-Proxy maintains the distributed network across all the nodes, 
pods, and containers and exposes the services across the outside world. It acts as a 
network proxy and load balancer for a service on a single worker node and manages 
the network routing for TCP and UDP packets.

