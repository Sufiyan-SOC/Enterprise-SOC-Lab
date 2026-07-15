# Hunt Name

Registry Persistence Hunting

---

## Objective

Identify Registry-based persistence mechanisms.

---

## Threat Hypothesis

An attacker may create or modify Registry Run Keys to execute malware automatically after user logon.

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 13

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder

---

## Hunt Procedure

1. Detect Registry Value Set events.
2. Review Run and RunOnce locations.
3. Validate Registry values.
4. Review responsible process.
5. Correlate with PowerShell activity.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
(TargetObject="*\\CurrentVersion\\Run\\*" OR TargetObject="*\\CurrentVersion\\RunOnce\\*")
| table _time Image TargetObject Details User
```

---

## Expected Findings

* Registry Run Key modifications
* Startup persistence entries
* Associated process

---

## IOC Examples

* Suspicious Run Keys
* Unknown startup executables
* AppData executable paths

---

## Investigation Guidance

Correlate Registry persistence with process creation, PowerShell execution, and Scheduled Tasks to identify multi-stage persistence.
