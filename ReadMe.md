# This repo will help us to build kubernetes cluster (one master and two worker nodes)

## Prereq:
- Please make sure to have your build server up and running, we will be using our build server to run ansible playbooks. ( Please clone VagrantBoxes and run steps to create a build server)
- A little understanding of ansible roles, atlease we by seeing existing tasks we should aware what this task is going to do


## Build one master and worker nodes using vagrant
Clone this repo to local and run below command to build new VM's 
`vagrant up`

Note: Make sure to power off any unused vm's

### Connect to this boxes using mobaxterm or putty 
Make sure to add private key while logging to this boxes.


### Install vagrant plugin to copy files from local to vagrant box
For some reasons I can't able to copy files manually so create a dummy jenkins job to copy files to our build server


### update host file and copy ssh keys
Update host file and append these entries
`sudo vi /etc/hosts`
192.168.50.10  master
192.168.50.11  worker1
192.168.50.12  worker2

#### copy ssh keys
ssh-copy-id vagrant@<allnodes>

### Update master node RAM to meet minumum requirement


## Run playbook to install kubernetes
`cd /var/lib/jenkins/workspace/checoutSourceCode`
`ansible-playbook -i ./ansible/inventories/hosts ./ansible/deployKubernetes.yaml`