# Cisco Hybrid Cloud CVD - Cisco HyperFlex and Red Hat OpenShift Container Platform (OCP)

This repository contains the Ansible automation for provisioning the on-prem data center infrastructure in the above Cisco Validated Design. The design and deployment guide for the CVD is available at: https://www.cisco.com/c/en/us/td/docs/unified_computing/ucs/UCS_CVDs/hx_rh_ocp_hybrid_cloud.html

## Solution Topology
The end-to-end topology for the solution is shown in the figure below:

![alt text](files/solution_topology.webp)

The Ansible playbooks provided in this repo will automate the on-prem compute, network and virtualization layer infrastructure in the solution. 

![alt text](files/Automation_topology.png)

## Ansible Directory Structure - Location of Playbooks, Inventory and Variables 
The playbooks, inventory files and variables for provisioning the on-prem infrastructure in the solution topology are located in the following files and directores:

* HyperFlex VSI Playbooks:  CVD_HC-OCP-HXFI/compute
* Networking Playbooks: CVD_HC-OCP-HXFI/network
* Inventory and Variables: CVD_HC-OCP-HXFI/inventory
  - Inventory file: inventory_main.ini
  - HyperFlex VSI Variables: group_vars/cisco_hx_fi, group_vars/cisco_intersight, group_vars/cisco_intersight_hx_std
  - Networking Variables: groups_vars/cisco_dc_fabric
