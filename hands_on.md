## Command to use after Deploying Kubernetes
 - To Check on Minikube version ===> $minikube version
 - To Start Minkube ====> $minikube start
 - To see Kubectl version ===> $kubectl version
 - To Get Cluster info ===> $kubectl cluster-info
 - To Get Nodes info ===> $kubectl get nodes
 - To Show all pods ===> $kubectl get pods
 - To Describe pods ===> $kubectl describe pods
 - To Execute a command directly ===> $kubectl exec $POD_NAME env
 
## Test the Cluster
 - sudo kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.4 --port=8080
 - sudo kubectl expose deployment hello-minikube --type=NodePort
 - sudo minikube service hello-minikube --url
 
## First Lab on Kubernetes
 - To list all docker commands ===> $sudo docker images 
 - To Get cluster info ====> $sudo kubectl cluster-info
 - To Get Dashboard address ====> $sudo minikube dashboard --url
 - To Get the Minkube address ====> $sudo minikube ip
 - To Build a Docker image from a Dockerfile ===> $sudo docker build -t hello-node:v1 .
 - To Create a Deployment the manage a POD ===> $kubectl run hello-node --image=hello-node:v1 --port=8000 --image-pull-policy=Never
 - To Get the Deployment status  ===> $sudo kubectl get deployments
 - To Get Pods  ====> $sudo kubectl get pods
 - To Expose the Pod as a kubernetes service to be visible outside ===> $sudo kubectl expose deployment hello-node --type=LoadBalancer
 - To get the List of Kubernetes Services ===> $kubectl get services
 - To Get the Logs of the application  ===> $kubectl logs <POD-NAME>
 - To Update the image in the Kubernetes Cluster ===> $kubectl set image deployment/hello-node hello-node=hello-node:v2
 - To List all Addons list ===> $minikube addons list
 - To Enable Heapster addons ===> $minikube addons enable heapster
 - To view the Pod and SVC just created ===> $kubectl get po,svc -n kube-system
 
## Deploy A Nodejs Application
 - To Deploy an image ===> $kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=6000
 - To Get all deployments ===> $kubectl get deployments
 
