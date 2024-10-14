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
18. kubectl get pods -0 wide --> shows which pod runs on which node

#### syntax
- kubectl <action> <objectType> <objectname>

