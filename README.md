# Enterprise Network Infrastructure

## Summary

This project is a network simulation using Cisco Packet Tracer to demonstrate a network design for a small and stable organization with five locations. It incorporates various protocols and technologies such as OSPF, DHCP, STP, LACP, HSRP, ACLs, VLANs, and BPDU guards.

**Note:** Only headquarters (HQ) locations have Finance, HR, and Tech departments, while other locations have HR and Tech.

## Protocols Implemented

1. **IP Addressing Scheme:**
   - Developed an efficient IP addressing scheme with subnetting to support up to 45+ hosts within the 10.0.0.0/16 network.
   - IP address assignments to hosts are managed by DHCP servers, which include options like subnet range, max-lease-time, address pool, and domain name. DHCP servers are located in the Tech department for each location.

2. **VLAN:**
   - Implemented VLANs to enable communication among hosts within the same department at each location, achieved through micro-segmentation of collision domains on the switches.
   - Two to three VLAN domains are implemented across every switch in the network.

3. **DNS:**
   - DNS servers are deployed within each Tech department to resolve hostname queries for routers connected to the location.
   - For example, a gateway router in the Boston department might be assigned the name BOR1, allowing hosts in Boston to ping the router using the hostname, not just the IP address.

4. **OSPF:**
   - Implemented OSPF to enable inter-location network connectivity.
   - HQ locations have backup gateways to prevent single-point failures, with HSRP providing redundancy within a local subnet.
   - The core network uses area 0, and all other locations are connected to this area.

5. **LACP:**
   - Deployed Ether channels with LACP in selected locations to ensure link redundancy and enhanced bandwidth.
   - Rapid STP has been implemented to prevent switching loops and broadcast flooding.

## Network Topology
