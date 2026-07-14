# Windows Scheduled Tasks

## Overview

Windows Scheduled Tasks automate program execution based on triggers such as user logon, system startup, or scheduled times. While widely used for system administration, attackers frequently abuse Scheduled Tasks to maintain persistence and execute malicious payloads.

---

## Data Source

* Microsoft Sysmon
* Process Creation Events

---

## Common Administrative Tool

schtasks.exe

---

## Important Investigation Fields

| Field       | Purpose                       |
| ----------- | ----------------------------- |
| User        | Account that created the task |
| Image       | Executed process              |
| ParentImage | Parent process                |
| Computer    | Endpoint                      |
| _time       | Event timestamp               |

---

## SOC Investigation Checklist

When investigating Scheduled Tasks:

1. Identify the user account.
2. Verify the parent process.
3. Validate the executable configured by the task.
4. Review task trigger.
5. Correlate with Registry and PowerShell activity.
6. Determine whether the task is legitimate or malicious.

---

## Common Suspicious Indicators

Scheduled Tasks launching:

* powershell.exe
* cmd.exe
* wscript.exe
* mshta.exe
* rundll32.exe

Or binaries from:

* %Temp%
* %AppData%
* C:\Users\Public

---

## MITRE ATT&CK

Technique:

T1053.005 – Scheduled Task / Job

---

## Key Takeaways

* Scheduled Tasks are a common persistence mechanism.
* IOC-based hunting helps identify known malicious tasks.
* Parent process and user context are critical during investigations.
* Timeline correlation provides valuable context for persistence analysis.
