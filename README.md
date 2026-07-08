# CSCE 3530 Network Project

## Project Title
Small Office Network Simulation Using Proxmox Virtual Machines

## Student
Zion Welsh

## Project Overview
This project simulates a small office-style network using Proxmox virtual machines. The network includes a router/firewall VM, an internal server VM, and two Ubuntu Desktop client VMs.

The Router-Firewall-VM provides routing, NAT, and firewall forwarding between the internal lab network and the outside home network. The Server-VM provides DHCP, DNS, and Apache web services. The two client VMs receive DHCP addresses, use the internal DNS server, access the hosted web page, and reach the internet through the router/firewall.

## Network Topology

| Device | Interface | IP Address | Purpose |
|---|---|---|---|
| Router-Firewall-VM | ens18 | 192.168.4.113/22 | Outside/home network |
| Router-Firewall-VM | ens19 | 192.168.10.1/24 | Internal gateway |
| Server-VM | ens18 | 192.168.10.10/24 | DHCP, DNS, Apache |
| Client-1-VM | ens18 | 192.168.10.100/24 | DHCP client |
| Client-2-VM | ens18 | 192.168.10.101/24 | DHCP client |

## Implemented Services

- DHCP using `isc-dhcp-server`
- DNS using BIND9
- Apache web server
- NAT using nftables
- ICMP connectivity testing
- DNS lookup testing
- HTTP web testing
- Traceroute path testing

## Repository Structure

```text
doc/
  Final report PDF, editable DOCX, and topology diagram

configs/
  Router, DHCP, DNS, and web server configuration files

screenshots/
  Router, server, and client verification screenshots
