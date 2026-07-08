# Day 1 – SOC Home Lab Planning & Virtualization Environment Setup

## Objective

The objective of this phase was to design and prepare the foundation for a complete SOC (Security Operations Center) Home Lab.

The lab environment was planned to simulate an enterprise network where Windows systems, Linux servers, Active Directory, and SIEM solutions would work together to support security monitoring, log analysis, threat detection, and incident investigation.

---

# Project Overview

This SOC Home Lab project is designed to simulate a real enterprise Security Operations Center environment.

The complete lab will include:

* Windows Server (Active Directory)
* Windows 11 Endpoint
* Ubuntu Server
* Splunk Enterprise SIEM
* Splunk Universal Forwarder
* Microsoft Sysmon
* Attack Simulation
* Detection Engineering
* Security Monitoring
* Incident Investigation

---

# Planned Lab Architecture

```text
                   SOC Home Lab

          Windows Server 2022
        (AD DS, DNS, DHCP Server)
                  │
                  │
        Internal Virtual Network
                  │
        ┌─────────┴─────────┐
        │                   │
        │                   │
 Windows 11 Endpoint    Ubuntu Server
                         (Splunk SIEM)
        │                   │
        │                   │
 Universal Forwarder    Security Monitoring
        │                   │
        └─────────► Splunk Enterprise ◄─────────┘
```

---

# Environment Preparation

Prepared the virtualization environment required for the SOC lab.

Environment planning included:

* Virtual machine architecture
* Network segmentation
* Operating system selection
* Resource allocation
* Storage planning
* Host communication design

---

# Software Planned

| Component                  | Purpose                                   |
| -------------------------- | ----------------------------------------- |
| Oracle VirtualBox          | Virtualization Platform                   |
| Windows Server 2022        | Active Directory Infrastructure           |
| Windows 11                 | Enterprise Endpoint                       |
| Ubuntu Server              | SIEM Server                               |
| Splunk Enterprise          | Security Information and Event Management |
| Splunk Universal Forwarder | Log Collection                            |
| Microsoft Sysmon           | Advanced Endpoint Telemetry               |

---

# Skills Learned

* SOC architecture planning
* Enterprise lab design
* Virtualization concepts
* Network planning
* Infrastructure design
* Cybersecurity lab preparation

---

# Deliverables

Successfully planned the complete SOC Home Lab environment with a structured roadmap for infrastructure deployment, centralized log collection, endpoint monitoring, and security operations.

---

# Outcome

A scalable and enterprise-style SOC Home Lab architecture was successfully planned.

This foundation will support the deployment of Active Directory, Windows endpoints, Ubuntu Server, Splunk Enterprise, Sysmon, detection engineering, attack simulations, and incident response workflows throughout the remaining phases of the project.

---

