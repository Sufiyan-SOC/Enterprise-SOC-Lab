# Detection Use Cases

## Overview

This directory contains the technical documentation for every security detection use case implemented in the Enterprise SOC Lab.

Each document represents a complete Security Operations Center (SOC) workflow, beginning with a controlled attack simulation and ending with investigation and incident documentation.

The objective is to demonstrate practical experience with detection engineering, security monitoring, security analysis, and incident response using Splunk Enterprise.

---

# SOC Detection Workflow

Every documented detection follows the same workflow:

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

Each detection use case contains:

- Attack Scenario
- Attack Simulation
- Log Source
- Detection Objective
- Detection Logic
- SPL Queries
- Alert Configuration
- Investigation Process
- MITRE ATT&CK Mapping
- Dashboard Design
- Incident Report
- Analyst Recommendations

---

# Current Detection Use Cases

| Detection Use Case | MITRE ATT&CK |
|--------------------|--------------|
| SMB Brute Force | T1110 |
| Local Account Discovery | T1087.001 |
| Network Share Discovery | T1135 |
| Remote Desktop Logon | T1021.001 |

> Additional enterprise detection use cases will be added as the lab expands.

---

# Purpose

The documentation in this directory demonstrates the complete lifecycle of enterprise security detections, from attack simulation to investigation and reporting.

Rather than focusing only on attack execution, each use case highlights how a SOC analyst detects, validates, investigates, and documents suspicious activity using Splunk Enterprise.

This approach reflects real-world Security Operations Center workflows and showcases practical blue-team skills relevant to SOC Analyst (L1) responsibilities.
