# Detection Name

Scheduled Task Persistence Detection

---

## Detection Purpose

Detect Scheduled Task creation that may be used to establish persistence or automate malicious execution.

---

## MITRE ATT&CK

Technique: **T1053.005 – Scheduled Task / Job**

---

## Data Source

Microsoft Sysmon

Event ID 1 – Process Creation

---

## Detection Logic

Monitor execution of **schtasks.exe**.

Review:

* User
* Parent process
* Command line
* Task name

Investigate tasks launching scripting engines or executables from user-writable directories.

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
Image="*schtasks.exe"
| table _time User ParentImage CommandLine
```

---

## Severity

High

---

## False Positives

* Enterprise automation
* Administrative maintenance
* Software deployment

---

## Triage Steps

1. Identify task creator.
2. Review task parameters.
3. Verify executable path.
4. Correlate with PowerShell or Registry activity.
5. Validate business justification.

---

## Recommended Analyst Actions

* Review Scheduled Task configuration.
* Investigate suspicious persistence.
* Escalate unauthorized task creation.
