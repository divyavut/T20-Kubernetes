#### Kubernetes Architecture 
Kubernetes (often abbreviated as K8s) is an open-source container orchestration platform developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF). It is designed to automate the deployment, scaling, and management of containerized applications across clusters of servers.
- it has two main objects
    - Master Node
    - Worker Node
#### Kubernetes Master Node Components
1. API server: Kube-apiserver 
  -  It acts as the front-end for the master node(control panel), exposing the Kubernetes APIs and handling authentication, authorization, and REST API requests from users. It maintains all API
  - API Server communicates with the etcd database to read and write the cluster's desired state.
2. Controller Manager ---> It is resposible for running the controller processes that monitors the worker nodes and make the adjustment to maintain the desired state. Each controller is resposible for ensuring that the state matches the desired configuration. It performs the self healing.mechanism by running the controller on the worker nodes.
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

##### Controller ( controller has a Control loop --> Observe,diff, action)
  - Deployments : how many pods are asked by user, it always ensure desired number of pods are available on the node. user: 10 pods; desired 
  - ReplicaSet 

#### Kubernetes Master Node other objects

5. kube-admin --> it is used to configure the master node
6. kubectl  ---> its a command line tool that interacts with the kubernetes API server and manage the kubernetes resources.
5. kube proxy --> is a network proxy service that runs on each node in a Kubernetes cluster. Its primary role is to maintain network connectivity to Kubernetes pods and services by implementing network rules, forwarding traffic, and load balancing


#### Kubernetes Worker Node component.
- Node is just a  pysical machine on the kubernetes cluster that runs the application workloads.
1. kubelet ---> kubelet is an agent that runs on each worker node and is resposible for managing and maintaining the state of that node. The primary role of kubelet is to ensure containers are running in pods as specified in the cluster's desired state.
2. kube proxy --> is a network proxy service that runs on each node in a Kubernetes cluster. Its primary role is to maintain network connectivity to Kubernetes pods and services by implementing network rules, forwarding traffic, and load balancing

#### 01 Workloads

#### Workload Pod
- pod will not have high availability, scalability, self healing


##### Workload Deployment and replicasset 
- deployment will provide high availability, scalibility,self healing by creating replicas of pods.
- In background, Deployment depends on replicaset. Along with deployment creation  corresponding replicaset will be created, it maintiances the version histroy of all changes we made for the pods in the deployment.
- By looking at the replica set of the deployment , we get the all version histroy of the pod.
- deployment controls the replicas set.
- replicasset will be created when deployment is created.
- If we delete the replicas et , we eill ,loss the histroy of all changes we made for the pod.
- Name of the pod is same as replica set but it has unique number at the end.

#### Services
- 


#### Service and deployment(selector and labels)
- Deployment creates Pods with the label app: nginx-deploy.
- Service has a selector that looks for Pods with the label 