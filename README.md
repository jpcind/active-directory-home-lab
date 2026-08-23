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

## Active Directory Structure

The Active Directory environment was organized using Organizational Units (OUs), domain users, and security groups.

## DNS Configuration

DNS was configured on the domain controller to support Active Directory name resolution and domain services.

- DC01 hosts the DNS service for the `homelab.test` domain.
- Domain-joined Windows 11 clients were configured to use DC01 as their DNS server.
- DNS resolution was verified using `nslookup`.
- Active Directory DNS service records were verified to confirm that clients could locate the domain controller.
- DNS and connectivity issues were troubleshot using tools such as:
  - `ipconfig /all`
  - `nslookup`
  - `ping`

### Organizational Units

- Employees
  - Engineering
  - Finance
- Groups

### Domain Users

- Charlie User
- Delta User
- Echo User

### Security Groups

- Leads-Users

The OU structure was used to organize users by department and prepare the environment for department-specific Group Policy configuration.

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
