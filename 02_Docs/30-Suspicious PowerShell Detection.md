# Day 30 — Suspicious PowerShell Detection

## Objective

Develop a Splunk detection use case to identify suspicious PowerShell execution on Windows endpoints using Sysmon Process Creation events.

The objective of this exercise was to simulate a real SOC workflow, beginning with detection engineering and ending with incident documentation.

---

# Scenario

PowerShell is one of the most commonly abused Windows utilities during post-exploitation.

Attackers frequently use PowerShell to:

- Execute malicious scripts
- Launch encoded commands
- Download payloads
- Evade detection
- Execute fileless attacks

To improve endpoint visibility, Sysmon Process Creation logs were collected into Splunk Enterprise and used to build a detection capable of identifying suspicious PowerShell activity.

---

# Lab Environment

| Component | Role |
|-----------|------|
| Windows Server 2022 | Active Directory, DNS, DHCP |
| Windows 11 Enterprise | Monitored Endpoint |
| Ubuntu Server | Splunk Enterprise |
| Sysmon | Endpoint Telemetry |
| Kali Linux | Attack Workstation |

---

# Workflow

Detection Rule

↓

SPL Query

↓

Alert

↓

Dashboard

↓

Attack Simulation

↓

Alert Trigger

↓

Dashboard Analysis

↓

Investigation

↓

Incident Report

---

# Detection Strategy

The detection focused on PowerShell executions containing command-line arguments frequently associated with attacker activity, including:

- EncodedCommand
- -enc
- -nop
- Hidden Window
- Invoke-WebRequest
- DownloadString

---

# Detection Outcome

The detection successfully identified suspicious PowerShell executions generated during the attack simulation.

Splunk provided complete visibility into:

- Executing endpoint
- User account
- Parent process
- Command line
- Execution timeline

The collected telemetry enabled a complete analyst investigation and incident documentation.

---

# Skills Demonstrated

- Windows Endpoint Monitoring
- Sysmon Log Analysis
- Splunk SPL Development
- Alert Engineering
- Dashboard Development
- Security Investigation
- Detection Engineering
- MITRE ATT&CK Mapping

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | PowerShell | T1059.001 |
