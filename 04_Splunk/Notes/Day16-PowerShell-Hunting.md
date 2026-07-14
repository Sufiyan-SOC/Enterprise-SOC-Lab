# Windows PowerShell Hunting

## Overview

PowerShell is a legitimate Windows administration framework that is widely used by system administrators. Because of its powerful scripting capabilities, it is also frequently abused by attackers for execution, persistence, lateral movement, and defense evasion.

---

## Data Source

Microsoft Sysmon

Process Creation Events

---

## Primary Process

powershell.exe

---

## Important Fields

| Field       | Description       |
| ----------- | ----------------- |
| Image       | Executed process  |
| ParentImage | Parent process    |
| User        | Executing account |
| Computer    | Endpoint          |
| _time       | Event timestamp   |

---

## Why Monitor PowerShell?

PowerShell is commonly used for:

* Administrative automation
* Malware execution
* File downloads
* Remote administration
* Post-exploitation activity

---

## SOC Investigation Checklist

* Verify the executing user.
* Review the parent process.
* Determine whether execution was expected.
* Correlate with Registry and Scheduled Task activity.
* Investigate additional endpoint events.
