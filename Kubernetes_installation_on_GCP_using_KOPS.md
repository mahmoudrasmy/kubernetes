# How To install Kubernetes Cluster using KOPS from Ubuntu

## Install Kubectl
 - $apt-get update
 - $curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.10.0/bin/linux/amd64/kubectl 
 - $chmod +x kubectl 
 - $kubectl /usr/local/bin/ 

## Install KOPS
 - curl -Lo kops https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64
 - chmod +x ./kops
 - mv ./kops /usr/local/bin/
