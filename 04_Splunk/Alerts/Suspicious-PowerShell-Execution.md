# Alert

## Alert Name

Suspicious PowerShell Execution

---

## Purpose

Detect PowerShell executions containing command-line arguments commonly associated with attacker activity.

---

## Platform

Splunk Enterprise

---

## Data Source

Sysmon Operational Log

Event ID 1

---

## Trigger Logic

Alert triggers when PowerShell is executed with:

- EncodedCommand
- -enc
- -nop
- -w hidden
- Invoke-WebRequest
- DownloadString

---

## Search

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
(CommandLine="*-enc*" OR CommandLine="*-EncodedCommand*" OR CommandLine="*DownloadString*" OR CommandLine="*Invoke-WebRequest*" OR CommandLine="*-nop*" OR CommandLine="*-w hidden*")
```

---

## Schedule

Every 5 Minutes

---

## Trigger

Results > 0

---

## Severity

High

---

## MITRE

Execution

T1059.001

---

## Analyst Response

- Validate command line
- Verify executing user
- Review parent process
- Determine legitimacy
