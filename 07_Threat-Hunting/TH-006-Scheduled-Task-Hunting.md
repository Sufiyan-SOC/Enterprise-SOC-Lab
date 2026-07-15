# Hunt Name

Scheduled Task Persistence Hunting

---

## Objective

Identify malicious Scheduled Tasks used for persistence or unauthorized automation.

---

## Threat Hypothesis

An attacker may create Scheduled Tasks to automatically execute malicious code after reboot or user logon.

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 1

---

## MITRE ATT&CK

T1053.005 – Scheduled Task / Job

---

## Hunt Procedure

1. Detect schtasks.exe execution.
2. Review ParentImage.
3. Analyze CommandLine.
4. Identify task creator.
5. Build execution timeline.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
Image="*schtasks.exe"
| table _time User ParentImage CommandLine
```

---

## Expected Findings

* Scheduled Task creation
* Task execution parameters
* Creating user

---

## IOC Examples

* PowerShell creating Scheduled Tasks
* Tasks executing from Temp or AppData
* Unexpected task creators
* Suspicious task names

---

## Investigation Guidance

Validate the Scheduled Task configuration and correlate it with PowerShell execution, Registry modifications, and other endpoint telemetry to determine whether persistence has been established.
