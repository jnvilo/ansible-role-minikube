# ansible-role-minikube

Installs :

1. minikube
2. helm 
3. kubectl 

Sets up systemd but this currently dies immmediately due to a problem with docker running as root. (See Running below) 

## Usage


- hosts: <HOSTNAME OR GROUPNAME>
  remote_user: ansible
  become: yes
 

  roles:
    - role: docker
    - role: minikube


## Running 

At this time, the systemd fails to start so start as normal use with: 

	    ansible@minikube-2:~$ minikube start --cpus=4 --memory=6g --addons=ingress
	😄  minikube v1.31.0 on Ubuntu 22.04 (kvm/amd64)
	✨  Using the docker driver based on existing profile
	❗  You cannot change the memory size for an existing minikube cluster. Please first delete the cluster.
	❗  You cannot change the CPUs for an existing minikube cluster. Please first delete the cluster.
	👍  Starting control plane node minikube in cluster minikube
	🚜  Pulling base image ...
	🏃  Updating the running docker "minikube" container ...
	🐳  Preparing Kubernetes v1.27.3 on Docker 24.0.4 ...
    	▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
	▪ Using image registry.k8s.io/ingress-nginx/controller:v1.8.1
	🔎  Verifying Kubernetes components...
	    ▪ Using image registry.k8s.io/ingress-nginx/kube-webhook-certgen:v20230407
	    ▪ Using image registry.k8s.io/ingress-nginx/kube-webhook-certgen:v20230407
	🔎  Verifying ingress addon...
	🌟  Enabled addons: storage-provisioner, default-storageclass, ingress
	🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default

