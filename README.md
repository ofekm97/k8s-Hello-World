# k8s-Hello-World

requirements:
* Minikube: https://minikube.sigs.k8s.io/docs/start/
* Kubectl: https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/
* Docker cluster to run minikube

minikube:
* Minikube start // starts the minikube and connects to the docker cluster
* (optional) minikube dashboard // for monitoring the minikube

kubectl:
* kubectl create deployment <deployment_name> --image=ofekm97/k8s-hello-world // pulles the image from docker hub
* kubectl expose deployment <deployment_name> --type=NodePort --port=3000 // create a service that expose the deployment to external IP address (3000 because the node server listen in port 3000)
* kubectl port-forward service/<deployment_name> <port_num>:3000 // access the application in the cluster from cluster port 3000 via localhost port <port_num>
  
go to http:/localhost:<port_num>/
