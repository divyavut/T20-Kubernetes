#### Kubernetes networking
1. VPC Network for Nodes
   - Type: VPC Network
   - Purpose: Enables communication between nodes within the cluster and provides external access (if configured).
   - Managed By: Cloud provider (e.g., AWS, GCP, Azure).
2. Cluster IP Network for Pods
   - Type: Cluster IP Network
   - Purpose: Enables internal communication between Pods within the cluster.
   - Managed By: CNI plugin (e.g., Calico, Flannel).
3. Containerd Bridge Network for Containers Inside Pods
  - Type: Bridge Network
  - Purpose: Allows communication between containers within the same Pod.
  - Managed By: Container runtime (e.g., Docker, containerd).

#### Insdie Pod
- default pause container will be created and it creates network interface card and attach it to 1. main container, 2. helper container.
- we cant see pause conatiner in the pod, it is hidden.

