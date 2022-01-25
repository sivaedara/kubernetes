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
`vagrant plugin install vagrant-scp`