# Day 1 – SOC Home Lab Planning & Virtual Infrastructure Setup

## Objective

The objective of this phase was to design and build the foundational infrastructure for a SOC Analyst Home Lab.

A virtual environment was planned to simulate an enterprise network where Windows and Linux systems could communicate securely. This infrastructure serves as the base for implementing Active Directory, SIEM, endpoint monitoring, log collection, threat detection, and incident investigation in the upcoming phases.

---

# Lab Architecture

```text
               SOC Home Lab

               Host Machine
                    │
        ┌───────────┴───────────┐
        │                       │
        ▼                       ▼
 Windows Server            Ubuntu Server
 (Domain Controller)      (Splunk SIEM)

        │
        │
        ▼
 Windows 11 Client
 (Domain Joined Endpoint)
```

---

# Environment Details

| Component               | Details              |
| ----------------------- | -------------------- |
| Virtualization Platform | Oracle VirtualBox    |
| Host Operating System   | Windows              |
| Server Operating System | Windows Server       |
| Client Operating System | Windows 11           |
| Linux Distribution      | Ubuntu Server        |
| Project Type            | SOC Analyst Home Lab |

---

# Tasks Completed

## 1. Planned the SOC Home Lab

* Defined the overall lab architecture
* Identified required virtual machines
* Planned network communication between systems
* Designed a scalable enterprise-style lab environment

---

## 2. Prepared Virtual Infrastructure

Created virtual machines for:

* Windows Server
* Windows 11 Client
* Ubuntu Server

Allocated appropriate CPU, RAM, storage, and network adapters for each virtual machine.

---

## 3. Designed Network Topology

Planned communication between:

* Windows Server
* Windows 11 Client
* Ubuntu Server
* Host Machine

Prepared the environment for future Active Directory and SIEM deployment.

---

## 4. Defined Project Roadmap

Planned upcoming implementation phases:

* Active Directory Deployment
* DNS & DHCP Configuration
* Domain Joining
* Linux Server Preparation
* Splunk Enterprise Deployment
* Windows Log Collection
* Sysmon Deployment
* Detection Engineering
* Incident Investigation
* MITRE ATT&CK Mapping

---

# Skills Learned

* Enterprise lab planning
* Virtual infrastructure design
* SOC architecture fundamentals
* Virtual machine deployment
* Network planning
* Project documentation

---

# Outcome

Successfully planned and prepared the SOC Home Lab infrastructure.

The virtual environment is ready for implementing enterprise services such as Active Directory, DNS, DHCP, SIEM deployment, endpoint monitoring, and centralized log management.

This foundation will support all future phases of the SOC Analyst Home Lab project.


