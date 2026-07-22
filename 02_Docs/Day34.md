# Detection Use Cases

## Overview

This directory contains the technical documentation for all security detection use cases implemented throughout the Enterprise SOC Lab.

Each document represents a complete Security Operations Center (SOC) workflow based on a controlled attack simulation performed within the lab environment. The documentation demonstrates how security events are detected, analyzed, investigated, and documented using Splunk Enterprise.

The objective is to showcase practical blue team skills aligned with real-world SOC Analyst responsibilities.

---

# Detection Workflow

Every documented use case follows a standardized SOC workflow:

Attack Scenario

↓

Attack Simulation

↓

Windows Event Generation

↓

Log Collection in Splunk

↓

Detection Rule

↓

SIEM Alert

↓

Alert Triage

↓

Investigation

↓

MITRE ATT&CK Mapping

↓

Dashboard Visualization

↓

Incident Report

---

# Documentation Standard

Each detection use case includes:

- Attack Scenario
- Attack Simulation
- Detection Objective
- Windows Log Source
- Detection Logic
- SPL Detection Queries
- SIEM Alert Configuration
- Alert Triage Process
- Investigation Methodology
- MITRE ATT&CK Mapping
- Dashboard Design
- Incident Report
- Analyst Notes
- Security Recommendations

---

# Current Detection Use Cases

| Detection Use Case | MITRE ATT&CK |
|--------------------|--------------|
| SMB Brute Force Detection | T1110 |
| Local Account Discovery | T1087.001 |
| Network Share Discovery | T1135 |
| Remote Desktop Logon Detection | T1021.001 |
| Windows Service Creation Detection | T1543.003 |

> Additional enterprise detection use cases will be added as the Enterprise SOC Lab continues to expand.

---

# Purpose

The purpose of this documentation is to demonstrate the complete lifecycle of enterprise security monitoring, from attack simulation through detection engineering, investigation, and incident reporting.

Rather than focusing solely on attack execution, each use case illustrates how a SOC Analyst validates security events, develops detections, performs investigations, maps adversary behavior to the MITRE ATT&CK Framework, and documents findings using enterprise SOC methodologies.

This documentation reflects practical Security Operations Center workflows commonly performed by Tier 1 Security Analysts in enterprise environments.
