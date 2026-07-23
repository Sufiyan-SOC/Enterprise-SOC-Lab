# Windows Service Creation Detection

## Overview

This document describes the complete Security Operations Center (SOC) workflow for detecting Windows service creation events that may indicate persistence or unauthorized software installation.

Windows services are commonly used by administrators for legitimate system management. However, attackers frequently abuse Windows services to establish persistence, execute malicious payloads, or maintain long-term access to compromised systems.

The objective of this use case is to demonstrate how Splunk Enterprise can detect Windows service creation events, support SOC investigations, and improve visibility into persistence techniques.

---

# Detection Objective

Identify newly created Windows services that could indicate persistence, unauthorized administrative activity, or post-exploitation behavior.

---

# Attack Scenario

A new Windows service was created on CLIENT1 using the Windows Service Control (sc.exe) utility.

The activity generated Windows Security and Sysmon events, allowing Splunk Enterprise to detect, investigate, and document the service creation process.

---

# Detection Workflow

Attack Simulation

↓

Windows Security Logs

↓

Microsoft Sysmon Logs

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

# Log Sources

- Microsoft Sysmon
- Windows Security Logs

---

# Detection Summary

The detection successfully identified:

- Windows service creation activity
- Service executable path
- Service name
- User responsible for service creation
- Endpoint where the service was installed

---

# Investigation Summary

The investigation confirmed that a new Windows service was created during a controlled lab simulation.

Splunk correlated Windows Security and Sysmon telemetry to identify the endpoint, user account, service name, executable path, and execution timeline.

The activity was validated as an authorized lab exercise and classified as a True Positive.

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Persistence | Create or Modify System Process: Windows Service | T1543.003 |

---

# Skills Demonstrated

- Attack Simulation
- Windows Event Log Analysis
- Microsoft Sysmon Monitoring
- Splunk Detection Engineering
- SIEM Alert Development
- SOC Alert Triage
- Incident Investigation
- MITRE ATT&CK Mapping
- Security Dashboard Development
- Incident Reporting
