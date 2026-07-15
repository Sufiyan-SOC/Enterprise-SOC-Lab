# Detection Name

Registry Run Key Persistence Detection

---

## Detection Purpose

Detect Registry Run and RunOnce modifications that may establish persistence.

---

## MITRE ATT&CK

Technique: **T1547.001 – Registry Run Keys / Startup Folder**

---

## Data Source

Microsoft Sysmon

Event ID 13 – Registry Value Set

---

## Detection Logic

Monitor modifications to:

* HKCU\Software\Microsoft\Windows\CurrentVersion\Run
* HKLM\Software\Microsoft\Windows\CurrentVersion\Run
* RunOnce Registry locations

Review:

* Modified Registry path
* Registry value
* Responsible process
* User account

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
(TargetObject="*\\CurrentVersion\\Run\\*" OR TargetObject="*\\CurrentVersion\\RunOnce\\*")
| table _time User Image TargetObject Details
```

---

## Severity

High

---

## False Positives

* Legitimate startup applications
* Software installation
* Administrative configuration

---

## Triage Steps

1. Verify Registry location.
2. Review Registry value.
3. Identify responsible process.
4. Correlate with PowerShell execution.
5. Review timeline.

---

## Recommended Analyst Actions

* Validate startup entry.
* Investigate persistence mechanism.
* Escalate unauthorized Registry modifications.
