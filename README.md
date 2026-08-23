# Active Directory Home Deployment

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

<img width="1536" height="1024" alt="AD Home Deployment" src="https://github.com/user-attachments/assets/b916a2f2-1e16-4d63-95ae-a664a4564e7c" />


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

## Screenshots

### Active Directory Users and OUs

**Engineering OU**

![Engineering Users](screenshots/AD%20-%20Engineering.png)

**Finance OU**

![Finance Users](screenshots/AD%20-%20Finance.png)

### Security Group

![Security Groups](screenshots/AD%20-%20Groups.png)

### Active Directory SRV Record Verification

![AD SRV Records](screenshots/ad%20srv%20records.png)

### Client Network Configuration

![Client IP Configuration](screenshots/client%20ip%20config.png)

### DNS Manager

![DNS Manager Zone](screenshots/dns%20manager%20zone.png)

### DNS Resolution

![DNS Resolution](screenshots/dns%20resolution.png)

### Additional DNS Verification

![DNS Resolution Additional](screenshots/dns%20resolution%20%282%29.png)

### Domain User Authentication

![Domain Authentication](screenshots/domain%20authentication.png)

### Group Policy Enforcement

![Engineering Control Panel Disabled](screenshots/engineering%20control%20panel%20disabled.png)

### Group Policy Configuration

![GPO Control Panel Disabled](screenshots/gpo%20control%20panel%20disabled.png)

## Troubleshooting

- Resolved DNS configuration issues by verifying that domain clients were using DC01 as their DNS server.
- Changed VirtualBox client networking from NAT to Bridged Adapter mode to allow proper communication with the domain controller on the local network.
- Troubleshot IPv4 and IPv6 DNS behavior to ensure Active Directory name resolution was directed to DC01.
- Verified Active Directory service discovery by querying LDAP SRV records with `nslookup`.
- Tested and verified Group Policy enforcement by applying a policy to the Engineering OU and confirming the restriction on a domain client.

## Project Outcomes

- Deployed and administered an Active Directory domain using Windows Server.
- Joined three Windows 11 client machines to the `homelab.test` domain.
- Configured and verified DNS for Active Directory name resolution and service discovery.
- Organized users using Organizational Units and security groups.
- Created and linked Group Policy to the Engineering OU and verified policy enforcement on a client machine.
- Troubleshot client networking, DNS configuration, and VirtualBox network connectivity.
- Verified domain authentication and Active Directory SRV records using Windows command-line tools.
