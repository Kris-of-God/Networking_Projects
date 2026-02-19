# VLAN Segmentation & Inter-VLAN Routing Lab

## Project Overview
This project demonstrates how to configure VLANs and enable communication between them using router-on-a-stick inter-VLAN routing in Cisco Packet Tracer. The network is segmented into two VLANs to simulate separate departments (Technical and Marketing) and improve network organization and security.

## Objectives
- Create VLANs
- Assign switch ports to VLANs
- Configure trunking
- Enable inter-VLAN routing
- Test connectivity
- Understand network segmentation

## Tools
- Cisco Packet Tracer
- 1 Router
- 1 Switch
- 2 PCs

## Network Topology
PC1 → Switch Fa0/1 → VLAN 10 (Technical)
PC2 → Switch Fa0/2 → VLAN 20 (Marketing)
Switch G0/1 → Router G0/0 (Trunk link)

## IP Addressing
PC1            192.168.10.10 (VLAN 10) 
PC2            192.168.20.10 (VLAN 20) 
Router         192.168.10.1  (VLAN 10) 
Router         192.168.20.1  (VLAN 20) 

## Testing Connectivity
Connectivity was tested using ping.
Ping from PC1 to PC2 was successful, confirming that inter-VLAN routing is working correctly.

## Verification Commands
Switch:
show vlan brief
show interfaces trunk

Router:
show ip interface brief

## Why VLAN Segmentation Matters
VLANs separate devices into different broadcast domains. This improves network performance and security by limiting unnecessary traffic and isolating devices.
For example, devices in Technical can be separated from devices in Marketing to prevent unauthorized access. Devices in different VLANs cannot communicate without routing, allowing network administrators to control traffic between networks.

## Results
- VLANs created successfully
- Ports assigned correctly
- Trunk link operational
- Inter-VLAN routing working
- Ping successful

## Key Concepts Learned
VLANs create separate broadcast domains
Trunks carry multiple VLANs
Routers enable VLAN communication
Segmentation improves security

## Screenshots
Screenshots included in this folder show:
- VLAN configuration
- Port assignments
- Trunk configuration
- Router configuration
- Successful ping test

  ## The Packet Tracer (.pkt) file is included so the lab can be opened and tested.
