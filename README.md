# 🛡️ Enterprise SOC Home Lab

## 📌 Overview

This project demonstrates the design and implementation of an Enterprise Security Operations Center (SOC) Home Lab. The lab simulates a real-world enterprise environment for Blue Team operations, including Active Directory administration, log collection, threat detection, threat hunting, and incident response.

The primary goal of this project is to gain hands-on experience with enterprise security tools and workflows commonly used by SOC Analysts.

---

## 🎯 Objectives

- Build an Enterprise Active Directory environment
- Configure DNS and DHCP services
- Deploy Windows and Linux systems
- Install and configure Splunk Enterprise
- Deploy Wazuh SIEM
- Configure Sysmon for enhanced Windows logging
- Simulate cyber attacks in a controlled lab
- Perform threat hunting and log analysis
- Map detections to the MITRE ATT&CK Framework
- Document security incidents

---

## 🏗️ Lab Architecture

```text
                 Internet (NAT)
                      │
        ┌────────────────────────┐
        │ Windows Server 2022    │
        │ DC01 (Domain Controller)│
        └─────────────┬──────────┘
                      │
          Internal Network (intnet)
      ┌───────────────┼───────────────┐
      │               │               │
 Windows 11      Ubuntu Server     Kali Linux
 Enterprise      Splunk + Wazuh    Attack Machine
```

---

## 🛠️ Technologies Used

- Windows Server 2022
- Windows 11 Enterprise
- Ubuntu Server
- Kali Linux
- Active Directory Domain Services
- DNS
- DHCP
- Splunk Enterprise
- Wazuh SIEM
- Sysmon
- PowerShell
- MITRE ATT&CK Framework
- VirtualBox

---

## 🔍 Lab Components

- Active Directory Domain Controller
- DNS & DHCP Services
- Windows Client Management
- Splunk SIEM
- Wazuh SIEM
- Sysmon Log Collection
- Attack Simulation
- Threat Hunting
- Incident Response
- Detection Engineering

---

## 📂 Repository Structure

```text
Enterprise-SOC-Lab/
│
├── Architecture/
├── Docs/
├── Screenshots/
├── Splunk/
├── Wazuh/
├── Detection-Rules/
├── Threat-Hunting/
├── MITRE-Mapping/
├── Incident-Reports/
├── Queries/
└── README.md
```

---

## 📚 Skills Demonstrated

- Active Directory Administration
- Windows Administration
- Network Configuration
- SIEM Deployment
- Windows Event Log Analysis
- Threat Hunting
- Incident Response
- Detection Engineering
- MITRE ATT&CK Mapping
- Security Monitoring

---

## 🚧 Project Status

**In Progress**

Current Phase:
- Building Enterprise Active Directory Environment

---

## 👨‍💻 Author

** Shaikh Sufiyan **

SOC Analyst | Blue Team | Cybersecurity Enthusiast
