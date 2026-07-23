# Day 32 - Network Share Discovery

## Overview

This document describes the complete Security Operations Center (SOC) workflow for detecting Windows Network Share Discovery activity.

Network share enumeration is commonly performed by attackers after obtaining initial access to identify accessible file shares, administrative shares, and valuable network resources. Monitoring this behavior helps SOC analysts identify reconnaissance activity that may precede lateral movement or data exfiltration.

The objective of this use case is to demonstrate how Splunk Enterprise can detect network share discovery commands using Microsoft Sysmon telemetry and support analysts during investigation.

---

# Detection Objective

Identify execution of Windows network share discovery commands such as:

- net view
- net use
- net share

using Microsoft Sysmon Process Creation events.

---

# Attack Scenario

An attacker executed Windows network discovery commands from a domain-joined workstation to enumerate available network shares and administrative resources.

The activity generated Sysmon Process Creation events that were collected by Splunk Enterprise and analyzed through detection rules, alerts, dashboards, and investigation workflows.

---

# Detection Workflow

Attack Simulation

↓

Windows Sysmon Logs

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

- Microsoft Sysmon
- Event ID 1 (Process Creation)

---

# Detection Summary

The detection successfully identified execution of Windows network discovery commands by monitoring:

- Process Name
- Parent Process
- Command Line
- Executing User
- Target Endpoint

---

# Investigation Summary

The investigation confirmed that Windows network share discovery commands were executed from the monitored endpoint.

Process creation telemetry provided complete visibility into the executed commands, associated parent process, execution timeline, and affected host.

The activity was verified as a controlled lab simulation and classified as a **True Positive**.

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | Network Share Discovery | T1135 |

---

# Skills Demonstrated

- Attack Simulation
- Windows Process Monitoring
- Microsoft Sysmon Analysis
- Splunk Detection Engineering
- SIEM Alert Development
- SOC Alert Triage
- Threat Investigation
- MITRE ATT&CK Mapping
- Security Dashboard Development
- Incident Reporting
