# Build Kubernetes cluster
`cd ./kubeclusterVMs`
`Vagrant up`

## Install kubelet in our local machine
curl -LO "https://dl.k8s.io/release/v1.23.0/bin/windows/amd64/kubectl.exe"
add new variable to yout path ( This is under environment variables)

## copy kubeconfig file from master node to our local machine
login to master copy config file in '/etc/kubernetes/admin.conf'

/etc/kubernetes/admin.conf    config

add to your path ( make sure to put file name also)
add new variable KUBECONFIG ( restart local windows shell)

## Install Helm  

download helm cli for windows
https://github.com/helm/helm/releases


### Installing prometheous
URL: https://prometheus.io/docs/visualization/grafana/
`helm repo add stable https://charts.helm.sh/stable`
`helm repo add prometheus-community https://prometheus-community.github.io/helm-charts`

=> `helm install kube-monitor  prometheus-community/kube-prometheus-stack -n monitoring`

From: https://www.fosstechnix.com/install-prometheus-and-grafana-on-kubernetes-using-helm/


nginx : https://artifacthub.io/packages/helm/bitnami/nginx

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install our-nginx bitnami/nginx -n nginx


helm pull bitnami/nginx

### Edit services as load balancers 
kubectl edit svc kube-monitor-kube-promethe-prometheus -n monitoring
kubectl edit svc kube-monitor-grafana

enable port in virtual box set up ( internal IP )