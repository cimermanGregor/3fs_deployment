# 3fs_deployment
Deploying system services and docker containers using Ansible on Ubuntu 16.04

## List of actions
Deployment procedure consists of following procedures:
- Update Ubuntu server
- Install and configure firewall on server
- Install and configure DNS with specific zone
- Install Docker and deploy simple PHP application

## Prerequisites 
Ubuntu server 16.04 for running services, Python2.7, PIP and git installed. The rest is installed by Ansible.

## Configuring parameters
Configuring services to fit in your environment you have to configure following variables
- iptables_ssh_networks: networks from which you allow SSH access to hosts
- iptables_trusted_networks: networks from which you allow any traffic
- iptables_public_ports: publicly available ports
- bind_zone: zone for DNS
- bind_records: DNS records in the zone file of format {name: x, type: [CNAME, A, AAAA,...] record: y}

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
For running playbook on the local host use localhost inventory
```shell
# ansible-playbook -i localhost site.yaml
```

## End result
TBD