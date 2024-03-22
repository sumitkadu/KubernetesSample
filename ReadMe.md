# Create Docker Image

docker build -t k8ssample-image -f DockerFile .

# Create Container

docker create --name core-k8ssample k8ssample-image

# Run Container App

docker run --rm -p 4040:4040 k8ssample-image

# Create Cluster and basic commands

$ kind create cluster --wait 5m \
$ export KUBECONFIG="$(kind get kubeconfig-path)" 
$ kubectl cluster-info
$ kind delete cluster

# Cluster Status

kubectl version
kubectl get componentstatuses

# Get Worker Nodes

kubectl get nodes
kubectl describe nodes <nodename>

# K8S Proxy

kubectl get daemonSets --namespace=kube-system kube-proxy

# K8S DNS

kubectl get deployments --namespace=kube-system core-dns

kubectl get services --namespace=kube-system core-dns

# K8S GUI

kubectl get deployments --namespace=kube-system kubernetes-dashboard
kubectl get services --namespace=kube-system kubernetes-dashboard
Kubectl proxy
