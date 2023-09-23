# haproxy-cluster-playbook
A highly available set (usually a triplet) of haproxies.

Powered by Pacemaker and HAProxy, this is intended to be run on normal machines - VMs or physical - to provide a highly available load balancer service, with optional niceties like TLS management and centralised TLS certificates.

## Requirements
* Ansible 2.12+ or greater.
* Standard Ubuntu or Debian hosts, running the latest or second-latest LTS release.

## Usage
* Copy inventories/dev to an inventories/ folder of your own.
* Within your inventories folder:
    * Edit the hosts file to point to your own hosts.
    * Edit the group_vars/loadbalancer.yml file to suit your needs.
* Install required roles using Ansible Galaxy:
    * `ansible-galaxy install -r requirements.yml`
* Run the playbook, pointing at your chosen inventory folder. Add --ask-become-pass if you do not use passwordless sudo.
    * `ansible-playbook site.yml -i inventories/dev`
