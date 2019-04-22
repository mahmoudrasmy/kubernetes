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
 
 ## Check on your GCP project and create bucket to save cluster state
  - gcloud config get-value project
  - gsutil mb gs://kubernetes-clusters-test-1/
 
 ## Install Kubernetes Cluster
 - PROJECT=`gcloud config get-value project`
 - export KOPS_FEATURE_FLAGS=AlphaAllowGCE # to unlock the GCE features
 - kops create cluster simple.k8s.local --zones us-central1-a --state gs://kubernetes-clusters-test-1/ --project=${PROJECT}
 - kops get cluster --state gs://kubernetes-clusters-test-1/ simple.k8s.local -oyaml
 - kops get instancegroup --state gs://kubernetes-clusters-test-1/ --name simple.k8s.local
 - kops update cluster simple.k8s.local --state gs://kubernetes-clusters-test-1/
 - kops get cluster --state gs://kubernetes-clusters-test-1/

## Delete the Cluster
 - kops delete cluster simple.k8s.local --state gs://kubernetes-clusters-test-1/
  
