# DHCP Configuration with VLANs

## Project Overview
This project demonstrates how to configure Dynamic Host Configuration Protocol (DHCP) in a VLAN-segmented network using Cisco Packet Tracer. The goal is to transition from a manually managed network (Static IP) to an automated, scalable environment using Dynamic Host Configuration Protocol (DHCP). Each VLAN has been configured with its own subnet and DHCP pool, just like in real-life enterprises.

## Skills Demonstrated
- Configuration of DHCP Pool
- Address exclusion (default Gateways)
- Automating IP address management
- VLAN-based network segmentation
- Network verification and testing

## Objectives
- Configure DHCP on a router
- Create DHCP pools for multiple VLANs
- Automatically assign IP addresses to devices
- Verify DHCP assignments
- Test network connectivity

## Tool(s) used
CISCO Packet Tracer
Router CLI

## Network Topology
The network consists of:
- 1 Router
- 1 Switch
- 2 PCs

## VLAN Configuration
- VLAN 10 (Technical): 192.168.10.0/24
- VLAN 20 (Marketing): 192.168.20.0/24

Each pool automatically provides the client with an 
- IP address
- the correct Subnet Mask
- the Default Gateway (the router’s sub-interface)
- a DNS Server (8.8.8.8).

## DHCP Configuration
### VLAN 10 (Technical) DHCP Pool

```
ip dhcp pool TECHNICAL
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 8.8.8.8
```

### VLAN 20 (Marketing) DHCP Pool

```
ip dhcp pool MARKETING  
network 192.168.20.0 255.255.255.0
default-router 192.168.20.1
dns-server 8.8.8.8
```

Each VLAN receives IP addresses automatically from its assigned DHCP pool.

## Address Exclusion
To protect the Router's interfaces, the gateway addresses were excluded from the DHCP pools
```
ip dhcp excluded-address 192.168.10.1 
ip dhcp excluded-address 192.168.20.1
```

## Verification Tests
### DHCP Binding Verification
`show ip dhcp binding`  command was used to verify DHCP assignments.
This command displays the IP addresses assigned to each device.

### Connectivity Test
Connectivity was tested using ping commands
Successful replies confirmed:
- DHCP is working
- VLANs are working
- Inter-VLAN routing is working

DHCP was successfully configured to automatically assign IP addresses to devices in different VLANs. Devices were able to communicate across VLANs using inter-VLAN routing.

## Screenshots
Screenshots included in this project:
- DHCP configuration
- VLAN configuration
- DHCP bindings (`show ip dhcp binding`)
- PC IP assignments
- Ping tests

## Benefits of DHCP
Automating IP assignment eliminates duplicate IP conflicts and ensures every device receives the correct Gateway and DNS settings automatically. This prevents human error.




