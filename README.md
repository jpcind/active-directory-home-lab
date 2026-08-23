# Active Directory Home Lab

## Overview

This project demonstrates the deployment and administration of a Microsoft Active Directory environment using Windows Server and Windows 11 virtual machines.

The lab includes:

* Windows Server Domain Controller
* Active Directory Domain Services (AD DS)
* DNS
* Windows 11 domain clients
* Organizational Units (OUs)
* Domain users and security groups
* Group Policy administration
* Domain authentication
* Network and DNS troubleshooting

## Lab Environment

**Domain:** `homelab.test`

**Domain Controller:** `DC01.homelab.test`

**Clients:**

* Charlie-LabAdmin
* Delta-LabAdmin
* Echo-LabAdmin

## Network Diagram

![Active Directory Home Lab Network Diagram](Active%20Directory%20Home%20Lab.png)

## Active Directory Structure

The Active Directory environment was organized using Organizational Units (OUs), domain users, and security groups.

### Organizational Units

* Employees

  * Engineering
  * Finance
* Groups

### Domain Users

* Charlie User
* Delta User
* Echo User

### User Placement

* Charlie User — Engineering
* Delta User — Engineering
* Echo User — Finance

### Security Groups

* Leads-Users

### Group Membership

* Charlie User — Leads-Users
* Echo User — Leads-Users

The OU structure was used to organize users by department and prepare the environment for department-specific Group Policy configuration.

## DNS Configuration

DNS was configured on the domain controller to support Active Directory name resolution and domain services.

* DC01 hosts DNS services for the `homelab.test` domain.
* Domain-joined Windows 11 clients were configured to use DC01 as their DNS server.
* DNS resolution was verified using `nslookup`.
* Active Directory DNS service records were verified to confirm that clients could locate the domain controller.
* DNS and network connectivity were troubleshot using:

  * `ipconfig /all`
  * `nslookup`
  * `ping`

## Domain Joining and Authentication

Three Windows 11 virtual machines were joined to the `homelab.test` Active Directory domain.

* Charlie-LabAdmin
* Delta-LabAdmin
* Echo-LabAdmin

Domain user accounts were tested by signing into the Windows 11 clients using Active Directory credentials.

The environment was also used to verify the distinction between standard domain users and administrative accounts.

## Lab Architecture

The lab was built using Oracle VirtualBox and consists of one Windows Server domain controller and three Windows 11 domain-joined client machines.

### Domain Controller

* Hostname: `DC01`
* Fully Qualified Domain Name: `DC01.homelab.test`
* Domain: `homelab.test`
* Roles:

  * Active Directory Domain Services
  * DNS
  * Group Policy Management

### Client Machines

* Charlie-LabAdmin
* Delta-LabAdmin
* Echo-LabAdmin

All three Windows 11 clients were joined to the `homelab.test` domain and configured to use the domain controller for DNS resolution.

## Network Configuration

The virtual machines were configured to communicate on the local `192.168.1.0/24` network.

* Default gateway: `192.168.1.1`
* Windows 11 clients were moved from VirtualBox NAT networking to bridged networking.
* Client DNS settings were configured to use the domain controller.
* IPv6 was disabled on the client machines during troubleshooting to ensure IPv4 DNS traffic was directed to DC01.
* Network connectivity was verified using `ping` and Windows network configuration tools.

## Group Policy

Group Policy Management was used as part of the Active Directory lab to explore centralized configuration of domain computers and users.

Group Policy work included preparation for department-specific policies associated with the Engineering and Finance organizational units.

The lab also included Group Policy and Windows Firewall testing related to ICMP echo requests.

## Troubleshooting and Verification

The environment was tested and troubleshot using built-in Windows networking and Active Directory tools.

Examples included:

* `ping` — verify network connectivity
* `ipconfig /all` — inspect IPv4, gateway, and DNS configuration
* `nslookup` — verify DNS name resolution
* Active Directory DNS SRV record verification
* Domain login testing
* DNS configuration troubleshooting
* IPv4 and IPv6 troubleshooting
* VirtualBox network adapter troubleshooting

Testing confirmed that the Windows 11 clients could locate the domain controller, resolve the `homelab.test` domain, and authenticate using domain accounts.

## Technologies

* Windows Server
* Windows 11
* Active Directory Domain Services
* DNS
* Group Policy
* Oracle VirtualBox

## Skills Demonstrated

* Active Directory administration
* Windows Server administration
* Domain controller deployment
* DNS configuration and troubleshooting
* Organizational Unit management
* User and security group administration
* Windows domain joining
* Domain authentication
* Group Policy administration
* IPv4 network configuration
* Network troubleshooting
* Virtual machine networking
