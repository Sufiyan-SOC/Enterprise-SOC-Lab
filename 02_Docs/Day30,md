# Day 30 — Suspicious PowerShell Detection

## Objective

Develop and validate a Splunk detection use case for identifying suspicious PowerShell execution on Windows endpoints using Sysmon Process Creation events.

This exercise focuses on detection engineering, security monitoring, alert validation, and incident investigation within the Enterprise SOC Lab.

---

# Scenario

PowerShell is one of the most frequently abused Windows utilities by adversaries for executing malicious payloads, downloading additional tools, establishing persistence, and performing post-exploitation activities.

To improve endpoint visibility, Sysmon Process Creation events were monitored in Splunk Enterprise and detection logic was developed to identify suspicious PowerShell command-line arguments.

---

# Environment

| Component | Role |
|-----------|------|
| CLIENT1 | Windows 11 Enterprise Endpoint |
| Ubuntu Server | Splunk Enterprise |
| Sysmon | Process Creation Logging |
| Kali Linux | Attack Workstation (Not used during validation) |

---

# Data Source

- Sysmon Operational Log
- Event ID 1 (Process Creation)

---

# Detection Strategy

The detection monitors PowerShell executions containing commonly abused command-line arguments such as:

- EncodedCommand
- -enc
- -nop
- Hidden Window
- Invoke-WebRequest
- DownloadString

These arguments are frequently associated with attacker tradecraft and are commonly observed during malware execution, fileless attacks, and post-exploitation.

---

# Detection Workflow

PowerShell Execution

↓

Sysmon Event ID 1

↓

Splunk Log Collection

↓

Detection Rule

↓

Alert Generation

↓

SOC Investigation

↓

Incident Documentation

---

# Splunk Components

## Detection Rule

DR-002 — Suspicious PowerShell Execution

---

## Alert

Suspicious PowerShell Execution

Severity: High

---

## Dashboard

Endpoint PowerShell Monitoring

Dashboard Panels:

- PowerShell Execution Trend
- Top Users
- Top Endpoints
- Suspicious Commands
- Recent Executions
- Parent Process Analysis

---

# Validation

Controlled PowerShell commands containing suspicious command-line arguments were executed to validate the detection rule.

The generated Sysmon events were successfully indexed into Splunk Enterprise and matched the detection logic.

The alert triggered successfully, confirming the rule was operating as expected.

---

# Investigation

The investigation verified:

- Endpoint
- Executing User
- Parent Process
- Full Command Line
- Execution Time
- Detection Trigger

The activity was confirmed as an authorized security validation performed within the Enterprise SOC Lab.

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | PowerShell | T1059.001 |

---

# Skills Demonstrated

- Detection Engineering
- Windows Endpoint Monitoring
- Sysmon Log Analysis
- Splunk SPL Development
- Alert Engineering
- Dashboard Development
- Security Investigation
- MITRE ATT&CK Mapping

---

# Outcome

Successfully designed, implemented, validated, and investigated a Splunk detection use case for suspicious PowerShell execution using Sysmon telemetry.

This use case demonstrates an end-to-end SOC workflow from endpoint telemetry collection to alert generation and incident investigation.
