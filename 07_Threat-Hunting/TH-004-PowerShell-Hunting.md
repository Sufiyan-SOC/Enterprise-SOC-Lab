# Hunt Name

PowerShell Execution Hunting

---

## Objective

Identify suspicious PowerShell execution across Windows endpoints.

---

## Threat Hypothesis

An attacker may leverage PowerShell to execute malicious commands, download payloads, or perform post-exploitation activities.

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 1

---

## MITRE ATT&CK

T1059.001 – PowerShell

---

## Hunt Procedure

1. Detect PowerShell execution.
2. Review ParentImage.
3. Analyze CommandLine.
4. Verify user context.
5. Build execution timeline.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
Image="*powershell.exe"
| table _time User ParentImage CommandLine
```

---

## Expected Findings

* PowerShell execution
* Parent process relationship
* Command-line arguments

---

## IOC Examples

* EncodedCommand
* DownloadString
* Invoke-WebRequest
* Hidden PowerShell execution

---

## Investigation Guidance

Review PowerShell execution together with Registry modifications, network activity, and Scheduled Task creation before determining malicious intent.
