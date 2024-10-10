#### Below steps told by charan sir(To run GKE Cluster from local machine need few tools)
1. Install gcloud CLI  command line tool and configure it in environment variables.
2. Install Kubernetes CLI is a command line interface and configure it in environment variables.
3. Install gke-gcloud-auth-plugin.
4. gcloud components install kubectl.



- The gcloud CLI is used by the user to authenticate and interact with Google Cloud services
- Kubernetes CLI is a command line interface to interact with kubernetes cluster
- The gke-gcloud-auth-plugin is a plugin for the kubectl command-line tool that facilitates authentication and allows interaction with Google Kubernetes Engine (GKE) on Google Cloud.
- kubectl is a command line tool to interact with  Kubernetes API server and manage the kubernetes resources


#### Steps to create google account,create cluster and connect to cluster from local laptob (Other way divya researched)
1. Create a GCP account
2. Install gcloud CLI  command line tool and configure it in environment variables.
3. Install kubectl command line tool.This commands includes kubectl and gke-gcloud-auth-plugin

       gcloud components install kubectl.
       
4. Create a Google  Kubernetes Engine
5. Set the active project: Run the following command to set the project context: 
        
           gcloud config set project [PROJECT_ID]
6. Get credentials for your Kubernetes cluster: Run this command to configure kubectl to use your cluster:

            gcloud container clusters get-credentials [CLUSTER_NAME] --zone [ZONE] --project [PROJECT_ID]
7. Verify the connection: You can check if you are connected to your cluster by running:
                kubectl get nodes

