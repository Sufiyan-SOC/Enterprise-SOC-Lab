# Detection Use Cases

## Overview

This directory contains documentation for each security detection use case implemented in the Enterprise SOC Lab.

Each document represents a complete SOC detection workflow based on a simulated attack performed in a controlled enterprise environment.

The objective is to demonstrate practical experience with detection engineering, security monitoring, investigation, and incident documentation using Splunk Enterprise.

---

# Detection Workflow

Every detection follows the same SOC workflow:

Attack Scenario

↓

Attack Simulation

↓

Windows Security Logs

↓

Splunk Log Collection

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
- Log Source
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

| Detection | MITRE |
|------------|--------|
| SMB Brute Force | T1110 |
| Local Account Discovery | T1087.001 |
| Network Share Discovery | T1135 |

Additional detection use cases will be added as the Enterprise SOC Lab expands.
