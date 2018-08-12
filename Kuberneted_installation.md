# How to install Kubernetes Locally 
$curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  <br>
$sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" <br>
$sudo apt-get update <br>
$apt-cache policy docker-ce <br>
$sudo apt-get install -y docker-ce <br>
$sudo systemctl status docker <br>
$curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo cp minikube /usr/local/bin/ && rm minikube <br>
$curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.10.0/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/ <br>
$minikube start --vm-driver=none <br>
