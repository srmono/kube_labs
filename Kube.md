sudo apt update
sudo apt install apt-transport-https
sudo apt upgrade

for vbox users:
sudo apt install virtualbox virtualbox-ext-pack

wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube


- minikube version

- install kubectl 

curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl


- Make the kubectl binary executable.
chmod +x ./kubectl


- Move the binary in to your PATH:

sudo mv ./kubectl /usr/local/bin/kubectl

kubectl version -o json  --client