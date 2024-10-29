#### Type Of Service
1. Cluster IP 
2. Node Port
3. Load Balancer

#### Cluster IP
- This service gets permanent IP(Internal IP), used for pod to pod communication. It will not get External IP
- when service is creating, it checks is there any pods with this label. selector tells that, if there any pods with this label.
- Once service is created to pods, pods are the endpoints to that service.
- it enables the internal acess communication.
- C

#### NodePort

- NodePort Service gets Internal IP and IT will not get External IP.
- Worker Node has Inetrnal IP and external IP.
- NodePort service opens a specify port on Node. so that we can accees the application using worker node External IP  and the port 
- Worker Node Port number is always > 32000.
- NodePort service is not secure to expose it to outside, it can used for testing purpose.

#### Load Balancer
- Load Balancer service gets an internal IP and Also External IP.
- LB service is secure, exposed but expensive.
- when loadbalancer ervice is created, kubernetes requests to the GCP to create a load balancer. that hpw th load balancer service get an external IP from load balancer.
- For every application, one laod balcer will be created, so it is so expensive

#### Note
- ClusterIP - Fully secured, not exposed
- NodePort  - Not Secure, Exposed
- LoadBalancer - Secured, Exposed, Expensive

- so here all three services has huddles and challenges.

#### To adress all above 
