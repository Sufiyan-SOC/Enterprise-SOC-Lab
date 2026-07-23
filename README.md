# 🛡️ Enterprise SOC Lab

## Enterprise Security Operations Center (SOC) Home Lab

This project demonstrates the design and implementation of an Enterprise Security Operations Center (SOC) Home Lab built inside Oracle VirtualBox.

The lab simulates a small enterprise Windows domain where security events are generated, collected, monitored, and investigated using Splunk Enterprise. The environment provides practical experience with Windows administration, Active Directory, centralized logging, security monitoring, attack simulation, alert development, and incident investigation.

The primary objective of this project is to develop hands-on Blue Team skills required for an entry-level SOC Analyst role by working with enterprise technologies and real-world security workflows.

---

# 🎯 Project Objectives

- Build an Enterprise Active Directory environment
- Configure Windows Server as a Domain Controller
- Deploy DNS and DHCP services
- Join Windows endpoints to the domain
- Deploy Splunk Enterprise
- Configure Splunk Universal Forwarder
- Deploy Microsoft Sysmon
- Centralize Windows Security and Sysmon logs
- Simulate attacks from Kali Linux
- Develop SPL detection use cases
- Build SIEM alerts and dashboards
- Investigate security events
- Map detections to the MITRE ATT&CK Framework
- Document security incidents

---

# 🏗️ Enterprise Lab Architecture

```text
                           Internet
                              │
                           NAT Network
                              │
                  ┌────────────────────────┐
                  │ Windows Server 2022    │
                  │ DC01                   │
                  │ Active Directory       │
                  │ DNS • DHCP             │
                  │ NAT + Internal         │
                  └────────────┬───────────┘
                               │
                     Internal Network
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
        │                      │                      │
 ┌──────────────┐      ┌────────────────┐     ┌──────────────┐
 │ Windows 11   │      │ Ubuntu Server  │     │ Kali Linux   │
 │ CLIENT1      │      │ Splunk SIEM    │     │ Attack VM    │
 │ Domain Joined│      │ Log Collection │     │ Attack Sim   │
 └──────────────┘      └────────────────┘     └──────────────┘
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

# ⚙️ Technologies

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
- Microsoft Sysmon
- Windows Event Logs
- PowerShell
- MITRE ATT&CK Framework

---

# 🔍 Enterprise Infrastructure

- Active Directory Domain
- Organizational Units (OU)
- Domain Users
- Domain Groups
- DNS Server
- DHCP Server
- Windows Domain Environment
- Domain Joined Windows Client

---

# 📊 Security Monitoring

- Windows Security Event Collection
- Microsoft Sysmon Event Collection
- Windows Authentication Monitoring
- Process Creation Monitoring
- RDP Authentication Monitoring
- Windows Service Monitoring
- Remote Command Execution Monitoring
- Network Share Discovery Monitoring

---

# 🚨 Security Detection Use Cases

The lab includes practical detection scenarios implemented using Splunk Search Processing Language (SPL).

Current detection use cases include:

- Windows Authentication Monitoring
- Brute Force Detection
- Network Share Discovery Detection
- Remote Desktop Logon Detection
- Windows Service Creation Detection
- Remote Command Execution Detection (Impacket PsExec)

Each detection includes:

- SPL Query
- SIEM Alert
- Dashboard
- Investigation
- MITRE ATT&CK Mapping
- Incident Report

---

# 🔄 SOC Investigation Workflow

Every simulated attack follows a structured SOC workflow.

```text
Attack Simulation
        │
        ▼
Windows Security Logs / Sysmon
        │
        ▼
Splunk Log Collection
        │
        ▼
Detection Rule (SPL)
        │
        ▼
SIEM Alert
        │
        ▼
Alert Triage
        │
        ▼
Investigation
        │
        ▼
MITRE ATT&CK Mapping
        │
        ▼
Dashboard Visualization
        │
        ▼
Incident Report
```

---

# 📂 Repository Structure

```text
Enterprise-SOC-Lab/

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

# 💼 Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Windows Endpoint Administration
- Splunk Enterprise Administration
- Splunk Search Processing Language (SPL)
- Splunk Alert Development
- Splunk Dashboard Development
- Windows Event Log Analysis
- Microsoft Sysmon Monitoring
- Security Monitoring
- Security Event Investigation
- Incident Analysis
- MITRE ATT&CK Mapping
- Blue Team Operations

---

# 🚧 Project Status

**Status:** Complete

This project demonstrates the deployment of an enterprise Windows environment and the implementation of a practical SOC workflow, including centralized logging, security monitoring, alert creation, dashboard development, security investigations, MITRE ATT&CK mapping, and incident documentation using Splunk Enterprise.

---

# 👨‍💻 Author

**Shaikh Sufiyan**

Aspiring SOC Analyst | Blue Team | Splunk | Active Directory | Windows Security

---

> This project was developed for hands-on learning, portfolio development, and demonstrating practical Security Operations Center (SOC) skills in an enterprise-style lab environment.
