# haproxy-cluster-playbook
A highly available set (usually a triplet) of haproxies

## Usage
* Fill out vars
* Fill out inventory
* `ansible-playbook site.yml -i ./inventories/dev/inventory --become --ask-become-pass`

## Configure Firewall

You can re-configure the haproxy servers firewalls easily with the 'ufw' tag:
`ansible-playbook site.yml -t 'ufw' -i ./inventories/dev/inventory --become --ask-become-pass`

## TODO
* Add support for multiple floating IPs, as it currently won't configure all of them for you.


## Quick Start Guide

1) Create a vars/secrets.yml file if running locally, fill in the {{ pacemaker_hacluster_password }} variable for the webUI.


2) Define the {{ corosync_bindnet_interface }} variable...