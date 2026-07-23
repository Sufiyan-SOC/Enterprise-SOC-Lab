# Remote Command Execution via Impacket PsExec

## Overview

This document describes the complete Security Operations Center (SOC) workflow for detecting and investigating remote command execution performed using Impacket PsExec.

Impacket PsExec is a legitimate administrative and penetration testing tool frequently abused by attackers to execute commands remotely over SMB during lateral movement.

The objective of this use case is to demonstrate how Splunk Enterprise can detect remote command execution using Microsoft Sysmon telemetry and support SOC analysts during investigation.

---

# Detection Objective

Identify remote command execution performed through Impacket PsExec by monitoring Sysmon Process Creation events and analyzing SYSTEM-level process activity.

---

# Attack Scenario

An attacker with valid domain credentials remotely executed commands on a Windows workstation using Impacket PsExec from the Kali attack machine.

The attack generated Windows process creation events, allowing the SOC to detect, investigate, and document the activity.

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

The detection identified:

- SYSTEM-level command execution
- Remote process creation
- Parent process information
- Executed command
- Affected endpoint

---

# Investigation Summary

The investigation confirmed that remote command execution originated from the Kali attack workstation using Impacket PsExec.

Sysmon Process Creation logs provided sufficient telemetry to identify the executed command, parent process, execution context, and destination endpoint.

The activity was validated as a controlled lab simulation and classified as a True Positive.

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Lateral Movement | SMB / Windows Admin Shares | T1021.002 |

---

# Skills Demonstrated

- Attack Simulation
- Windows Event Analysis
- Microsoft Sysmon Monitoring
- Splunk Detection Engineering
- SIEM Alert Development
- SOC Alert Triage
- Incident Investigation
- MITRE ATT&CK Mapping
- Security Dashboard Development
- Incident Reporting
