# Build Kubernetes cluster
`Vagrant up`


## Install kubelet in our local machine

curl -LO "https://dl.k8s.io/release/v1.23.0/bin/windows/amd64/kubectl.exe"

add to yout path

## copy kubeconfig file
update permissions 
`sudo  chmod 666 /etc/kubernetes/admin.conf`
login to master copy config file in '/etc/kubernetes/admin.conf'

/etc/kubernetes/admin.conf    config

add to your path ( make sure to put file name also)
add new variable KUBECONFIG ( restart local windows shell)

## Install Helm  

download helm cli for windows
https://github.com/helm/helm/releases


### Installing prometheous
URL: https://prometheus.io/docs/visualization/grafana/
helm repo add stable https://charts.helm.sh/stable
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm install our-prometheous  prometheus-community/kube-prometheus-stack

From: https://www.fosstechnix.com/install-prometheus-and-grafana-on-kubernetes-using-helm/


nginx : https://artifacthub.io/packages/helm/bitnami/nginx

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install our-nginx bitnami/nginx -n nginx


helm pull bitnami/nginx

### Edit services as load balancers 
kubectl edit svc stable-kube-prometheus-sta-prometheus -n monitoring
kubectl edit svc stable-grafana

enable port in virtual box set up ( internal IP )