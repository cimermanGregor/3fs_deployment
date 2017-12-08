# 3fs_deployment
Deploying system services and docker containers using Ansible on Ubuntu 16.04

## List of actions
Deployment procedure runs following procedures:
- Update Ubuntu server
- Installs and configures DNS with specific zone
- Installs and configures firewall on server
- Installs Docker and deploys image containing PHP application

## Disclamer
Work in progress.

## Prerequisites 
Ubuntu server 16.04 for running services, Python2.7, PIP and git installed. The rest is installed by Ansible.

## Configuring parameters
Configurig services to fit in your environment you have to configure following variables
- iptables_ssh_networks: networks from which you allow SSH access to hosts
- iptables_trusted_networks: networks from which you allow any traffic
- iptables_public_ports: publicly available ports

## Deployment procedure
Make sure the repository is located on host and change directory to it. Next step is to use ansible playbooks to do all the heavy lifting. We have to setup the environment.
```shell
# cd ansible
# virtualenv .venv
# source .venv/bin/activate
# pip install -r requirements.txt
```
Run the Ansible playbook to configure our host
```shell
# ansible-playbook -i production site.yaml
```
If you are running playbook on the host you would like to provision use localhost inventory.
```shell
# ansible-playbook -i localhost site.yaml
```

## End result
TBD