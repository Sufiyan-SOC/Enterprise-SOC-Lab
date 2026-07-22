# Day 31 – Local Account & Privileged Group Discovery Detection

## Objective

The objective of this exercise was to simulate an attacker performing post-compromise reconnaissance on a Windows endpoint and build an end-to-end SOC detection workflow using Splunk Enterprise.

After gaining initial access, attackers commonly enumerate local accounts, security groups, and administrative privileges before attempting privilege escalation or lateral movement. This activity is mapped to the MITRE ATT&CK Discovery tactic.

---

# Attack Scenario

A simulated attacker executed Windows native discovery commands from a compromised domain-joined workstation to identify:

- Current logged-in user
- Local user accounts
- Group memberships
- Local administrators

The objective was to generate Windows telemetry and validate that the activity could be detected, investigated, and documented using Splunk Enterprise.

---

# Attack Commands

```cmd
whoami

hostname

whoami /groups

net user

net localgroup administrators
```

---

# Environment

| Component | Role |
|----------|------|
| Windows Server 2022 | Active Directory Domain Controller |
| Windows 11 Enterprise | Target Endpoint |
| Ubuntu Server | Splunk Enterprise |
| Kali Linux | Attack Simulation |

---

# Log Source

The executed commands generated:

- Microsoft Sysmon
- Event ID 1 (Process Creation)

These events were forwarded to Splunk Enterprise through the Splunk Universal Forwarder.

---

# Detection Strategy

A Splunk SPL detection rule was developed to identify execution of account and group discovery commands.

Detection focuses on identifying execution of:

- whoami.exe
- net.exe

These binaries are frequently abused during the Discovery phase of an intrusion.

---

# Detection Workflow

Attack Simulation

↓

Sysmon Process Creation

↓

Splunk Log Collection

↓

Detection Rule (SPL)

↓

SOC Alert

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

# Investigation

The investigation focused on identifying:

- Host executing the commands
- User account involved
- Parent process
- Executed command line
- Timeline of activity

The collected evidence confirmed execution of Windows discovery commands from the monitored endpoint.

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Discovery | T1087.001 – Local Account Discovery |
| Discovery | T1069.001 – Local Group Discovery |

---

# Detection Outcome

The simulated attack was successfully detected using Splunk Enterprise.

The generated telemetry enabled identification of:

- Account discovery activity
- Local administrator enumeration
- User context
- Command execution timeline

---

# Skills Demonstrated

- Windows Security Monitoring
- Sysmon Log Analysis
- Splunk SPL Development
- Detection Engineering
- Security Event Investigation
- MITRE ATT&CK Mapping
- SOC Alert Triage
- Incident Documentation
