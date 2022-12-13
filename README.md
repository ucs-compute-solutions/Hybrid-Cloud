# Cisco Hybrid Cloud CVD - Cisco HyperFlex and Red Hat OpenShift Container Platform (OCP)

This repository contains the Ansible automation for provisioning the on-prem data center infrastructure in the above Cisco Validated Design. The design and deployment guide for the CVD is available at: https://www.cisco.com/c/en/us/td/docs/unified_computing/ucs/UCS_CVDs/hx_rh_ocp_hybrid_cloud.html

## Solution Topology
The end-to-end topology for the solution is shown in the figure below:

![alt text](files/solution_topology.webp)

The Ansible playbooks provided in this repo will automate the on-prem compute, network and virtualization layer infrastructure in the solution. The playbooks will do the day-2 configuration necessary to support a new Application HyperFlex VSI and day0-1 provision of the HyperFlex VSI cluster. 

![alt text](files/Automation_topology.png)

## Ansible Directory Structure - Playbooks, Inventory and Variables 
The playbooks, inventory files and variables for provisioning the on-prem infrastructure in the solution topology are located in the following files and directores:

### Cisco HyperFlex VSI

![alt text](files/location_hxvsi_topology.png)

### Cisco ACI

![alt text](files/location_aci_topology.png)

## Execution Workflow

1. Setup an Ansible Control Node - you will use this workstation to run the ansible playbooks
2. From a terminal window, navigate to the directory where you'd like to clone the above GitHub repo to. The playbooks are located in the https://github.com/ucs-compute-solutions/Hybrid-Cloud repository. 
3. From the terminal window, run the following command to clone the repo. 
```
https://github.com/ucs-compute-solutions/Hybrid-Cloud.git
```
4. Navigate to the **CVD_HC-OCP-HXFI** directory. You will find the playbooks for HyperFlex VSI playbooks and Cisco ACI in the in the **compute** and **network** sub-directories. 
5. Update the inventory file and variables file shown in the figure above with networking information for your environment. 
6. Navigate to the **network** sub-directory and execute the main network playbook as shown below:
```
CVD_HC-OCP-HXFI $ ansible-playbook network/00_main_deploy_dc-fabric.yml -i inventory/inventory_main.ini
```
7. Update the inventory file and variables file shown in the figure above with HyperFlex VSI information for your environment. 
8. Navigate to the **compute** sub-directory and execute the main compute playbook as shown below:
```
CVD_HC-OCP-HXFI $ ansible-playbook compute/00_main_deploy_hx-std.yml -i inventory/inventory_main.ini
```