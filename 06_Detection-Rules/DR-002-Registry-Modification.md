# Detection Name

Windows Registry Modification Detection

---

## Detection Purpose

Detect Registry modifications that may indicate persistence, configuration changes, or malicious activity.

---

## MITRE ATT&CK

Technique: **T1112 – Modify Registry**

---

## Data Source

Microsoft Sysmon

Event ID 13

---

## Detection Logic

Monitor Registry Value Set events and review:

* Modified Registry path
* Responsible process
* Registry value
* User account

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
| table _time Image TargetObject Details User
```

---

## Severity

Medium

---

## False Positives

* Windows updates
* Software installation
* Administrative configuration changes

---

## Triage Steps

1. Verify Registry path.
2. Identify responsible process.
3. Validate Registry value.
4. Correlate with nearby endpoint events.

---

## Recommended Analyst Actions

* Confirm change legitimacy.
* Investigate unexpected Registry locations.
* Escalate suspicious persistence indicators.
