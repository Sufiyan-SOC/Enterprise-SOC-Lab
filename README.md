# 🛡️ Enterprise SOC Lab

## Enterprise Security Operations Center (SOC) Home Lab

An enterprise-style Security Operations Center (SOC) Home Lab built to gain hands-on experience with Windows infrastructure, Active Directory administration, centralized log management, security monitoring, detection engineering, and incident investigation using Splunk Enterprise.

This project simulates a small enterprise environment where Windows endpoints generate security telemetry that is collected, analyzed, and investigated using real SOC workflows.

The primary goal of this lab is to demonstrate practical Blue Team skills required for an entry-level SOC Analyst role.

---

# Key Highlights

- Enterprise Active Directory Environment
- Windows Server 2022 Domain Controller
- DNS & DHCP Infrastructure
- Windows 11 Domain Client
- Splunk Enterprise SIEM Deployment
- Splunk Universal Forwarder Configuration
- Microsoft Sysmon Deployment
- Windows Security Log Collection
- Attack Simulation from Kali Linux
- Detection Engineering using SPL
- Security Monitoring
- Alert Development
- Dashboard Development
- Incident Investigation
- MITRE ATT&CK Mapping
- Incident Documentation

---

# Lab Architecture

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

# Technologies

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

# Enterprise Infrastructure

- Active Directory Domain
- Organizational Units
- Domain Users
- Domain Groups
- DNS Server
- DHCP Server
- Domain Joined Windows Client
- Enterprise Windows Environment

---

# Security Monitoring

- Windows Security Event Collection
- Sysmon Event Collection
- Authentication Monitoring
- Process Creation Monitoring
- Windows Service Monitoring
- Remote Command Execution Monitoring
- RDP Logon Monitoring
- Network Share Discovery Monitoring

---

# Detection Engineering

The project includes enterprise detection use cases developed using Splunk Search Processing Language (SPL).

Implemented detections include:

- Windows Authentication Monitoring
- Brute Force Detection
- Network Share Discovery Detection
- RDP Logon Detection
- Windows Service Creation Detection
- Remote Command Execution Detection (Impacket PsExec)

Each detection includes:

- SPL Query
- Alert Logic
- Dashboard
- Investigation
- MITRE ATT&CK Mapping
- Incident Report

---

# SOC Investigation Workflow

Every detection follows a structured SOC investigation process.

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

# Repository Structure

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

# Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Windows Endpoint Administration
- Splunk Enterprise Administration
- Windows Log Analysis
- Microsoft Sysmon
- Detection Engineering
- SIEM Alert Development
- Dashboard Development
- Security Event Investigation
- Incident Response Documentation
- MITRE ATT&CK Mapping
- Blue Team Operations

---

# Project Status

**Status:** Version 1.0 Completed

This project demonstrates an end-to-end enterprise SOC workflow, including infrastructure deployment, centralized logging, detection engineering, security monitoring, investigation, dashboard creation, MITRE ATT&CK mapping, and incident reporting.

Future enhancements may include additional enterprise detection use cases and expanded SOC automation.

---

# Author

**Shaikh Sufiyan**

Aspiring SOC Analyst | Blue Team | Splunk | Active Directory | Detection Engineering

---

> This project was built for learning, portfolio development, and demonstrating practical SOC Analyst skills in an enterprise-style lab environment.
