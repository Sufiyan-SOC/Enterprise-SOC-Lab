# Enterprise SOC Lab Architecture

## Purpose

This lab simulates a small enterprise network to gain practical experience in Security Operations Center (SOC) workflows. The environment focuses on Active Directory administration, centralized log collection, security monitoring, attack simulation, and incident investigation using Splunk Enterprise.

---

## Core Components

### Windows Server 2022 (DC01)

Role:
- Active Directory Domain Controller
- DNS Server
- DHCP Server

Network:
- NAT
- Internal Network

---

### Windows 11 Enterprise (CLIENT1)

Role:
- Domain Joined Workstation
- Security Event Source

Network:
- Internal Network

---

### Ubuntu Server

Role:
- Splunk Enterprise
- Central Log Collection

Network:
- NAT
- Internal Network
- Host-Only Adapter

---

### Kali Linux

Role:
- Attack Simulation Machine

Network:
- NAT
- Internal Network

---

## Log Flow

Windows Client

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

Detection

↓

Threat Hunting

↓

Incident Investigation
