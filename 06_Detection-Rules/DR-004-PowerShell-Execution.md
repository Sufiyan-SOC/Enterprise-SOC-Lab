# Detection Name

Windows PowerShell Execution Detection

---

## Detection Purpose

Detect execution of PowerShell to identify suspicious scripting activity, post-exploitation behavior, and administrative abuse.

---

## MITRE ATT&CK

Technique: **T1059.001 – PowerShell**

---

## Data Source

Microsoft Sysmon

Event ID 1 – Process Creation

---

## Detection Logic

Monitor execution of **powershell.exe** and review:

* Executing user
* Parent process
* Command line
* Endpoint

Investigate PowerShell launched from uncommon parent processes or containing suspicious command-line arguments.

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
Image="*powershell.exe"
| table _time Computer User ParentImage CommandLine
```

---

## Severity

Medium

---

## False Positives

* IT administration
* Automation scripts
* Enterprise management tools

---

## Triage Steps

1. Identify the executing user.
2. Review ParentImage.
3. Analyze CommandLine.
4. Verify execution purpose.
5. Correlate with Registry or Scheduled Task activity.

---

## Recommended Analyst Actions

* Validate administrative activity.
* Investigate suspicious PowerShell execution.
* Escalate if malicious behavior is confirmed.
