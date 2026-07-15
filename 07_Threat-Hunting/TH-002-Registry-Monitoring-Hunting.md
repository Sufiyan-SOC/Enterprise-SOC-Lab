# Hunt Name

Windows Registry Monitoring

---

## Objective

Identify Registry modifications that may indicate persistence or unauthorized configuration changes.

---

## Threat Hypothesis

An attacker may modify Windows Registry values to establish persistence or alter system behavior.

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 13

---

## MITRE ATT&CK

T1112 – Modify Registry

---

## Hunt Procedure

1. Detect Registry Value Set events.
2. Review modified Registry paths.
3. Identify responsible process.
4. Validate Registry value.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
| table _time Image TargetObject Details User
```

---

## Expected Findings

* Registry modifications
* Responsible process
* Modified Registry path

---

## IOC Examples

* Unexpected Registry keys
* Persistence-related Registry locations
* Suspicious executable paths

---

## Investigation Guidance

Correlate Registry activity with PowerShell execution, Scheduled Tasks, and process creation events.
