#### Kubernetes Architecture 
Kubernetes (often abbreviated as K8s) is an open-source container orchestration platform developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF). It is designed to automate the deployment, scaling, and management of containerized applications across clusters of servers.
- it has two main objects
    - Master Node
    - Worker Node
#### Kubernetes Master Node Components
1. API server: Kube-apiserver 
  -  It acts as the front-end for the master node(control panel), exposing the Kubernetes APIs and handling authentication, authorization, and REST API requests from users
  - API Server communicates with the etcd database to read and write the cluster's desired state.
2. Controller Manager ---> It is resposible for running the controller processes that monitors the worker nodes and make the adjustment to maintain the desired state. Each controller is resposible for ensuring that the state matches the desired configuration. It performs the self healing.mechanism. 
  - ReplicationController
  - ReplicaSet
  - Deployment Controller
  - DaemonSet Controller
  - StatefulSet Controller
  - Job Controller
  - CronJob Controller
  - Horizontal Pod Autoscaler (HPA) Controller
  - Node Controller 
  - Service Controller
  - Ingress Controller
  - EndpointSlice Controller
  - Custom Controllers
3. Scheduler --->  Scheduler is responsible for assigning pods to available nodes in the cluster based on resource requirements, affinity rules, and other factors.
4. ectd   ---> It is a distributed key value store that maintains the entire state of kubernetes clusetr including details about the services, pod, nodes and more.

#### Kubernetes Master Node other objects

5. kube-admin --> it is used to configure the master node
6. kubectl  ---> its a command line tool that interacts with the kubernetes API server.
5. kube proxy --> is a network proxy service that runs on each node in a Kubernetes cluster. Its primary role is to maintain network connectivity to Kubernetes pods and services by implementing network rules, forwarding traffic, and load balancing


#### Kubernetes Worker Node component.
- Node is just a  pysical machine on the kubernetes cluster that runs the application workloads.
1. kubelet ---> kubelet is an agent that runs on each worker node and is resposible for managing and maintaining the state of that node. The primary role of kubelet is to ensure containers are running in pods as specified in the cluster's desired state.
2. kube proxy --> is a network proxy service that runs on each node in a Kubernetes cluster. Its primary role is to maintain network connectivity to Kubernetes pods and services by implementing network rules, forwarding traffic, and load balancing
