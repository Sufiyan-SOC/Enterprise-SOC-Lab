# Remote Desktop Logon Detection

## Overview

This document describes the complete Security Operations Center (SOC) workflow for detecting and investigating Remote Desktop Protocol (RDP) logon activity within the Enterprise SOC Lab.

Remote Desktop is a legitimate administrative service commonly used by system administrators. However, it is also one of the most frequently abused remote access techniques by attackers after obtaining valid credentials.

The objective of this use case is to demonstrate how Splunk Enterprise can detect RDP logon events, support analyst investigation, and identify potential unauthorized remote access.

---

# Detection Objective

Detect successful Remote Desktop logon events and provide visibility into user authentication, source system activity, and endpoint access.

---

# Attack Scenario

A Remote Desktop connection was established to CLIENT1 using valid domain credentials from another system within the lab environment.

The activity generated Windows Security authentication events that were collected and analyzed in Splunk Enterprise.

---

# Detection Workflow

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

# Log Source

- Windows Security Event Log
- Event ID 4624 (Successful Logon)
- Logon Type 10 (Remote Interactive)

---

# Detection Summary

The detection identified:

- Successful RDP authentication
- Target endpoint
- Authenticated user
- Logon type
- Source IP Address
- Authentication timeline

---

# Investigation Summary

The investigation confirmed a successful Remote Desktop session to CLIENT1 using valid domain credentials.

Splunk Enterprise correlated authentication logs to identify the destination endpoint, authenticated user account, logon type, and source IP address.

The activity was validated as an authorized lab simulation and classified as a True Positive.

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Lateral Movement | Remote Services: Remote Desktop Protocol | T1021.001 |

---

# Skills Demonstrated

- Windows Authentication Analysis
- Remote Desktop Monitoring
- Splunk Detection Engineering
- SIEM Alert Development
- SOC Alert Triage
- Incident Investigation
- MITRE ATT&CK Mapping
- Dashboard Development
- Incident Reporting
