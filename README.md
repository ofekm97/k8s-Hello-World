# k8s-Hello-World

requirements:
* Minikube: https://minikube.sigs.k8s.io/docs/start/
* Kubectl: https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/
* Docker cluster to run minikube

minikube:
* Minikube start // Starts the minikube on the docker cluster
* (optional) minikube dashboard // Used for monitoring the minikube

kubectl:
* kubectl create deployment <deployment_name> --image=ofekm97/k8s-hello-world // Pulles the image from docker hub
* kubectl expose deployment <deployment_name> --type=NodePort --port=3000 // Create a service that expose the deployment (image) to external IP address (3000 because the node server listen in port 3000)
* kubectl port-forward service/<deployment_name> <port_num>:3000 // Access the application in the cluster from cluster port 3000 via localhost port <port_num>
  
go to http:/localhost:<port_num>/



# Upload your image to gcp
first, you will need to set a paying account in gcp.
open gcp cloud console:
* clone your project
* build you docker image
* upload your image to the container registry
* create a GKE cluster
* run:
    * kubectl apply -f deployment.yaml
    * kubectl apply -f service.yaml
