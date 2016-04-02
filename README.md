# Docker Machine Swarm cluster with Ansible

This set of ansible playbooks creates a docker swarm cluster with docker-machine and collects afterwards the information for all machines and put them together into a in memory playbook for further provisioning with ansible.

The cluster creation depends on this blog article: https://medium.com/on-docker/toward-a-production-ready-docker-swarm-cluster-with-consul-9ecd36533bb8#.viyt6j7rr

## How to use it
The easiest way is to vagrant up and use the the setup_machines.yml and infra.yml playbooks afterwards.
If you have real machines adjust the /ansible/hosts/server_list.yml file. Everything else gets dynamically generated.

## Attention
cleanup_machines.yml will remove all docker machines on your system and spin up the new ones (if anybody can tell me how to just delete the ones that are in list would be nice).
TODO: when it works to clean machines from the server_list.yml put this into the setup_machines.yml

## TODOs:
  - Add the consul containers
  - Add labels to the nodes for creating specifix containers on specific nodes
  - Make it more dynamic so other drivers except the generic drivers can be used

## Credits:
Viktor Farcic https://github.com/vfarcic - Using some of his roles of his playbooks and mentoring
Jacob Blain Christen https://github.com/dweomer - Article about setting up docker swarm cluster with docker machine
