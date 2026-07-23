# Day 14 – Sysmon Process Creation Investigation

## Overview

This phase focused on validating Microsoft Sysmon Process Creation events within Splunk Enterprise and understanding how process execution telemetry can be used during SOC investigations.

The objective was to verify endpoint visibility, analyze process creation events, and understand parent-child process relationships commonly reviewed by SOC analysts during incident investigations.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Splunk Enterprise 10.4.0 |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint | CLIENT1 |
| Windows User | sbish |
| Microsoft Sysmon | Installed |
| Sysmon Add-on | Installed |
| Splunk Universal Forwarder | Configured |

---

# Objectives

- Validate Sysmon log collection in Splunk
- Investigate Process Creation events (Event ID 1)
- Analyze process execution telemetry
- Understand parent-child process relationships
- Verify Windows endpoint visibility

---

# Microsoft Sysmon

Microsoft Sysmon extends native Windows logging by providing detailed endpoint telemetry.

For SOC analysts, Sysmon improves visibility into process execution, command-line activity, parent-child relationships, and endpoint behavior that are often unavailable through standard Windows Security logs.

---

# Event Covered

| Event ID | Description |
|----------|-------------|
| 1 | Process Creation |

---

# Activities Performed

The following Windows processes were executed and successfully collected by Splunk through Sysmon logging:

- Notepad
- Command Prompt
- PowerShell

Each execution generated a Process Creation event that was validated within Splunk Enterprise.

---

# Process Relationship Analysis

One of the primary goals of this exercise was to understand how Windows launches processes.

Normal execution example:

```text
explorer.exe
│
├── notepad.exe
├── cmd.exe
└── powershell.exe
```

Examples of suspicious process relationships that may require investigation:

```text
winword.exe
│
└── powershell.exe
```

```text
excel.exe
│
└── cmd.exe
```

These execution chains are commonly reviewed during malware and post-exploitation investigations.

---

# Investigation Summary

Sysmon successfully recorded Windows process creation activity.

Splunk provided visibility into:

- Executed process
- Parent process
- Command line
- Logged-on user
- Endpoint hostname
- Execution timestamp

This information enables SOC analysts to reconstruct process execution timelines and identify potentially suspicious activity.

---

# Skills Demonstrated

- Microsoft Sysmon Monitoring
- Windows Process Investigation
- Process Creation Analysis
- Parent-Child Process Analysis
- Splunk Log Investigation
- Endpoint Visibility Validation

---

# Outcome

The lab successfully validated Microsoft Sysmon Process Creation logging within Splunk Enterprise.

The environment can now be used to investigate Windows process execution and support future detection engineering use cases involving PowerShell abuse, command execution, remote administration tools, and post-exploitation techniques.

---

# Key Takeaways

- Sysmon Event ID 1 provides detailed process creation telemetry.
- Parent-child relationships are critical during endpoint investigations.
- Command-line logging significantly improves analyst visibility.
- Splunk enables efficient investigation of endpoint process activity.
- Process creation telemetry forms the foundation for multiple SOC detection use cases.
