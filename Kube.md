Intall minikube: 

sudo apt update
sudo apt install apt-transport-https
sudo apt upgrade

- for vbox users:
sudo apt install virtualbox virtualbox-ext-pack

wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube

minikube version

- install kubectl 

curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl


- Make the kubectl binary executable.
chmod +x ./kubectl

- Move the binary in to your PATH:

sudo mv ./kubectl /usr/local/bin/kubectl

kubectl version -o json  --client

--------------------------

# Install helm 
curl -LO https://get.helm.sh/helm-v3.8.2-linux-amd64.tar.gz 
tar -zxvf helm-v3.8.2-linux-amd64.tar.gz  

sudo mv linux-amd64/helm  /usr/local/bin/helm

helm version --short

----------------
# now on which cluster you want to install apps we have only one cluster

kubectl config view 

# add helm repo and create demo-mysql 

helm repo add stable https://charts.helm.sh/stable

helm install demo-mysql stable/mysql

kubectl get all | grep mysql 

---------------------------

# cleaning helm / uninstall helm

kubectl get all | grep mysql 

kubectl get secret | grep demo-mysql
-- note: we can delete by using kubectl , its not advisable 

# uninstall mysql with helm
helm uninstall demo-mysql

# run again and check 
kubectl get all | grep mysql 
kubectl get secret | grep demo-mysql

---------------------------------

# Building a Guest-Book helm chart










