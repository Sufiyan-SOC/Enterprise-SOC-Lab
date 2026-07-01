Day 3 – Active Directory Domain Services (AD DS)

Objective

Install Active Directory Domain Services and promote the Windows Server 2022 machine to a Domain Controller.

Prerequisites

- Windows Server 2022 installed
- Computer renamed to DC01
- Static IP configured

Steps Performed

1. Configured Static IP

- IP Address: 172.16.0.0
- Subnet Mask: 255.255.255.0
- DNS: 127.0.01

2. Installed AD DS Role

- Opened Server Manager
- Selected Add Roles and Features
- Installed Active Directory Domain Services

3. Promoted Server to Domain Controller

- Created a new forest
- Domain Name: corp.local
- Configured DSRM password
- Restarted the server

Verification

- Active Directory Users and Computers opened successfully.
- DNS Manager opened successfully.
- Domain Controller was created successfully.

Screenshots

1. Static IP configuration
2. AD DS installation
3. Domain Controller promotion
4. Active Directory Users and Computers
5. DNS Manager

Result

Windows Server 2022 was successfully promoted to a Domain Controller for the "corp.local" domain.
