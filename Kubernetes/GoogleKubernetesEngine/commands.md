#### Commands
1. kubectl config current-context 
2. kubectl config use-context <clustername>
3. kubectl cluster-info 
4. kubectl api-resources --list all native api
5. kubectl get nodes  --> get request
6. kubectl apply ---> post request
7. kubectl edit ---> patch/put request
8. kubectl delete --> delete method
9. kubectl get nodes -v 6 --> indetails api request information
10. kubectl get nodes -v 7
11. kubectl get nodes -v 7
12. kubectl apply -f yamlfile -v 7
13. kubectl get pods
14. kubectl delete pod pod_name -v 7 
15. kubectl describe pod pod_name
16. kubectl get pods -n kube-system
    - kubectl describe pod <podname> -n <namespace>
17. kubectl get pods -w(waiting)
18. kubectl get pods -o wide --> shows which pod runs on which node
19. kubectl get ingress ---> We dont have any ingress funcationaly in kubernetes.

#### syntax
- kubectl <action> <objectType> <objectname>

#### Ingress
- Thrid party application have to be installed in kubernetes to gets the the ingress functionality
- nginx Ingress controller developed by nginx.
- isto ingress controller developed by isto.
- HAproxy ingress controller developed by HAProxy.
- Kubernetes ingress controller developed by kubernetes.
#### Load Balancer 
- Azure 
  1. Layer 4 load Balancer : Azure LoadBalancer  
   - Basic load balancer ---> 1. just forward the request --> nosecurity checks. 2. 10 lb for  10 application
                          
  2. Layer 7 load Balancer : Application Gateway
   - Advanced load balncer --> encrpted request from user can be decrypted by load balancer, just forward th plain test to the server, this reduces the burnden on server. 1. 1 LB for many app.
   - we have  Routing rules 
     1. hostname based ---> dev.divyavutakanti.com/nginx
     2. path pbased -----> mysql.dev.divyavutaknti.com

- AWS 
  1. Layer 4 load Balancer : Network LoadBalancer
  2. Layer 7 load Balancer : Application LoadBalancer 
- GCP 
  1. Layer 4 load Balancer : Network LoadBalancer
  2. Layer 7 load Balancer : Application LoadBalancer.



  ##### Ingress Controller 
  - It is a controller object like deployment
  - Ingress controller is a controller  manages the special type of resource(object) called Ingress resource.
  - Ingress -(Custom Resource Definition)
  - Its a infrastructure supporting application.
  - Single Ingress controller manages multpile application.
  

  ##### Ingress rules
  1. Path Based Rule
   - (user)100.10.23.4/nginx ---->(Loadbalncer)100.10.23.4 ---> nginx-server(clusterIP) ---> nginx-deplyment---> micro service.
  2. Hostname based 
   - (user)www.nginx.com -----> (Loadbalncer)100.10.23.4 ---> nginx-server(clusterIP) ---> nginx-deplyment---> micro service.


##### Steps to work on Ingress controller 
- install ingress contoller in kubernetes
- create ingress resource crd(custom resource definition) which has rules based on condition, it perform action(forward the request to the server)
- ingress controller monitors the  ingress resources.


#### Namespace
- Do logical partition in the cluster. ResourceQuota is used to allocate resources for the namespace.
- 3 workers nodes - 6 vcpus - 12GB RAM
- Usecase: 
  1. Resource control : allocate the resuroece quota, request limits for containers in Cluster.
  2. Role BAsed Access control(RBAC) : STrict authorisation for development application, testing application, prod applications.
  3. Network communication control ---> I want to restrict comminution bet multiple applications

- default NameSpace , kube-system: stores cluster related resources, kube-public.

#### RBAC
- **Steps for authetication and authorisation**: 
   **Gcp Authentication:** User interact with Cloud platform(GCP)(server) Authentication handles through gcpCLI Tool(client)
   **Gcp Authorisation:**  User gets permission to perform action on specific resources(cluster) in the GCP authorisation managed through IAM.
   **Kubectl authetication:** kubectl(client) interact with  kube-APIServer(kubernetes cluster) authentication handles though ~/.kube/config.
   **Kubectl authorisation:** User gets permission to perform action on specific resource(pods,deploymenst....) within in the cluster manges through Role-Based Access Control (RBAC).

   