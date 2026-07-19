# 🛡️ Enterprise SOC Lab

## 📌 Overview

This project documents the design and implementation of an Enterprise Security Operations Center (SOC) home lab built inside VirtualBox.

The lab simulates a small enterprise Windows domain where security events are collected, centralized, and investigated using Splunk Enterprise. The environment is designed to provide hands-on experience with Active Directory administration, Windows event logging, Sysmon telemetry, security monitoring, attack simulation, and incident investigation.

The primary objective of this project is to gain practical Blue Team experience by building, managing, and monitoring an enterprise-style environment instead of relying only on theoretical knowledge.

---

# 🎯 Project Objectives

- Build an enterprise Windows Active Directory environment
- Deploy a centralized Domain Controller
- Configure DNS and DHCP services
- Join Windows clients to the domain
- Deploy Splunk Enterprise as the central SIEM
- Configure Splunk Universal Forwarder
- Deploy Sysmon for enhanced endpoint telemetry
- Collect Windows Security and Sysmon logs
- Simulate attacks from Kali Linux
- Investigate security events using SPL queries
- Build detection use cases
- Document incidents and findings

---

# 🏗️ Enterprise Lab Architecture

```text
                           Internet
                              │
                       NAT Network
                              │
                  ┌──────────────────────┐
                  │ Windows Server 2022  │
                  │ DC01                 │
                  │ Domain Controller    │
                  │ DNS • DHCP           │
                  │ NAT + Internal       │
                  └──────────┬───────────┘
                             │
                  Internal Network (intnet)
      ┌──────────────────────┼──────────────────────┐
      │                      │                      │
      │                      │                      │
┌──────────────┐     ┌────────────────┐     ┌──────────────┐
│ Windows 11   │     │ Ubuntu Server  │     │ Kali Linux   │
│ Enterprise   │     │ Splunk         │     │ Attack VM    │
│ CLIENT1      │     │ SIEM           │     │ NAT + Internal│
│ Internal     │     │ NAT + Internal │     └──────────────┘
└──────────────┘     └────────────────┘
```

---

# 🖥️ Lab Environment

| System | Role |
|---------|------|
| Windows Server 2022 | Active Directory Domain Controller |
| Windows 11 Enterprise | Domain Joined Client |
| Ubuntu Server | Splunk Enterprise SIEM |
| Kali Linux | Attack Simulation Machine |

---

# ⚙️ Technologies Used

- Windows Server 2022
- Windows 11 Enterprise
- Ubuntu Server
- Kali Linux
- Oracle VirtualBox
- Active Directory Domain Services
- DNS
- DHCP
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- PowerShell
- Windows Event Logs
- MITRE ATT&CK Framework

---

# 🔍 Current Lab Capabilities

### Enterprise Infrastructure

- Active Directory Domain
- Organizational Units (OU)
- Domain Users
- Domain Groups
- DNS
- DHCP
- Domain Joined Windows Client

### Security Monitoring

- Splunk Enterprise
- Universal Forwarder
- Windows Security Event Collection
- Sysmon Event Collection
- Windows Authentication Monitoring

### Attack Simulation

- Kali Linux Attack Machine
- SMB Authentication Testing
- Network Reconnaissance
- Windows Security Event Generation

### Investigation

- Windows Security Log Analysis
- Sysmon Investigation
- SPL Queries
- Authentication Event Investigation
- Source IP Identification

---

# 📂 Repository Structure

```text
Enterprise-SOC-Lab

├── 01_Architecture
├── 02_Docs
├── 03_Screenshots
├── 04_Splunk
│   ├── Alerts
│   ├── Dashboards
│   ├── Lookups
│   ├── Notes
│   ├── SPL-Queries
│   └── Saved
├── 06_Detection-Rules
├── 07_Threat-Hunting
├── 08_Incident-Reports
├── 09_MITRE-ATT&CK
└── README.md
```

---

# 🧩 Security Components

Current log sources include:

- Windows Security Logs
- Sysmon Operational Logs
- Windows Authentication Events
- Process Creation Events
- Network Connection Events

---

# 🧠 Skills Demonstrated

- Enterprise Active Directory Administration
- Windows Server Administration
- Windows Client Administration
- Splunk Enterprise Deployment
- Splunk Universal Forwarder Configuration
- Sysmon Deployment
- Windows Event Log Analysis
- Security Monitoring
- Threat Investigation
- Detection Engineering Fundamentals
- MITRE ATT&CK Mapping
- Blue Team Operations

---

# 🚧 Current Project Status

**Status:** In Progress

Completed:

- Enterprise Lab Deployment
- Active Directory Infrastructure
- Windows Domain Environment
- Splunk Enterprise Deployment
- Universal Forwarder Deployment
- Sysmon Configuration
- Windows Log Collection
- Initial Security Monitoring
- Initial Attack Simulation
- Authentication Event Investigation

The project is continuously being expanded with new attack scenarios, detection logic, dashboards, threat hunting queries, and incident reports.

---

# 👨‍💻 Author

**Shaikh Sufiyan**

Blue Team | SOC Analyst (Aspiring) | Cybersecurity Enthusiast
