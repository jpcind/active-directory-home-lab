# Active Directory Home Lab

## Overview

This project demonstrates the deployment and administration of a Microsoft Active Directory environment using Windows Server and Windows 11 virtual machines.

The lab includes:

- Windows Server Domain Controller
- Active Directory Domain Services (AD DS)
- DNS
- DHCP
- Windows 11 domain clients
- Organizational Units (OUs)
- Users and security groups
- Group Policy
- Domain authentication
- Network and DNS troubleshooting

## Lab Environment

Domain:

homelab.test

Domain Controller:

DC01.homelab.test

Clients:

- Charlie-LabAdmin
- Delta-LabAdmin
- Echo-LabAdmin

## Network Diagram

![Active Directory Home Lab Network Diagram](Active%20Directory%20Home%20Lab.png)

## Lab Architecture

The lab was built using Oracle VirtualBox and consists of one Windows Server domain controller and three Windows 11 domain-joined client machines.

### Domain Controller
- Hostname: DC01
- Domain: homelab.test
- Roles:
  - Active Directory Domain Services
  - DNS
  - DHCP
  - Group Policy Management

### Client Machines
- Charlie-LabAdmin
- Delta-LabAdmin
- Echo-LabAdmin

All Windows 11 clients were joined to the homelab.test domain and configured to use the domain controller for DNS resolution.

## Technologies

- Windows Server
- Windows 11
- Active Directory Domain Services
- DNS
- DHCP
- Group Policy
- PowerShell
- Oracle VirtualBox
