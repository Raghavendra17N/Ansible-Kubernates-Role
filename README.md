# Ansible-Kubernetes-Role
Just Clone the Respositroy to Set up Kubernetes Cluster in Ubuntu OS

## Installation
```bash
git clone https://github.com/Raghavendra17N/Ansible-Kubernates-Role.git
ansible-playbook k8s.yml
```
## Setting Up Inventory and k8s.yml
##### Set the Inventory with host and user
```bash
[k8s_master]
master ansible_ssh_host=[HostIP/hostname]  ansible_user=[user name]

[k8s_worker]
node ansible_ssh_host=[HostIP/hostname] ansible_user=[user name] 
```
##### Configure the k8s.yml with user
```bash
---
- hosts: all
  remote_user: [user]
  become: true
  roles:
    - Kubernetes
```
## Create the Group Vars in /etc/ansible/group_vars
#### Each file for each group[k8s_master and k8s_worker]
k8s_master group file
```bash
---
Kubernetes: master
```
k8s_worker group file
```bash
---
Kubernetes: node
```

## Usage
```bash
ansible-playbook k8s.yml
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.






