# Enterprise-SOC-Lab
Enterprise SOC Lab built using Active Directory, Windows Server, Splunk, Wazuh, Sysmon, Kali Linux, and MITRE ATT&amp;CK for threat detection, incident response, and threat hunting.

# Enterprise SOC Lab

## Project Overview

This project demonstrates the design and implementation of a home-based Enterprise Security Operations Center (SOC) lab for Blue Team learning and SOC Analyst practice.

The lab will simulate real-world enterprise environments using Active Directory, Windows, Linux, Wazuh, Splunk, Sysmon, and Kali Linux. Various cyber attacks will be executed in a controlled lab to generate logs, detect threats, investigate incidents, and practice incident response.

---

## Objectives

- Build an Enterprise SOC Home Lab
- Learn Active Directory Administration
- Collect Windows and Linux logs
- Configure Wazuh SIEM
- Configure Splunk Enterprise
- Perform Threat Hunting
- Simulate Cyber Attacks
- Create Detection Rules
- Map attacks to MITRE ATT&CK
- Write Incident Reports

---

## Technologies Used

- VirtualBox
- Windows Server 2022
- Windows 11
- Ubuntu Server
- Kali Linux
- Wazuh
- Splunk Enterprise
- Sysmon
- Active Directory
- MITRE ATT&CK

---

## Project Status

🟡 In Progress

Current Phase:
- [ ✓] Project Planning
- [✓ ] Virtual Lab Setup
- [✓ ] Active Directory
- [ ] Windows Client
- [ ] Splunk
- [ ] Wazuh
- [ ] Attack Simulation
- [ ] Threat Hunting
- [ ] Incident Response
- [ ] Documentation

---

## Author

Shaikh Sufiyan 


---

# Progress Log

## Day 1

### Completed
- Created project folders
- Created GitHub repository
- Downloaded required ISOs
- Installed VirtualBox

Status: ✅ Completed

---

## Day 2

### Windows Server 2022 Installation

Completed Tasks:
- Created VirtualBox VM
- Installed Windows Server 2022 Standard (Desktop Experience)
- Allocated 3 GB RAM and 60 GB Disk
- Configured Administrator account
- Renamed server to DC01

Status: ✅ Completed

---

## Day 3 Progress

### Active Directory Domain Services

Completed tasks:

- Configured Static IP
- Installed Active Directory Domain Services
- Promoted server to Domain Controller
- Created new forest: corp.local
- Verified AD DS and DNS installation

Status: ✅ Completed

---
Day 4 – Windows 11 Client Domain Join

Progress

- Created a Windows 11 virtual machine in VirtualBox.
- Installed Windows 11 Enterprise.
- Configured the network settings.
- Joined the client machine to the "corp.local" Active Directory domain.
- Verified successful domain authentication using a domain user account.
- Confirmed connectivity with the Domain Controller (DC01).

Status: ✅ Completed
----

SOC Analyst Aspirant
