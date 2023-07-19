# ansible-role-minikube

Installs minikube on server. 

## Usage


- hosts: <HOSTNAME OR GROUPNAME>
  remote_user: ansible
  become: yes
 

  roles:
    - role: docker
    - role: minikube

       

