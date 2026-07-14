# Incident Report

## Incident Title

Windows Registry Modification Investigation

---

## Summary

Registry modification events were investigated using Microsoft Sysmon Event ID 13. The analysis focused on identifying Registry changes, validating the responsible process, and confirming whether the activity represented legitimate administrative behavior.

---

## Data Source

Microsoft Sysmon

Event ID 13

---

## Investigation Findings

* Registry Value Set events were successfully collected.
* The responsible process was identified.
* Registry paths and stored values were validated.
* No malicious persistence or unauthorized Registry modifications were identified during the investigation.

---

## Severity

Low

Controlled Laboratory Activity

---

## MITRE ATT&CK

T1112 – Modify Registry

---

## Analyst Conclusion

Registry activity matched expected laboratory operations. The investigation demonstrated the ability to detect and analyze Registry modifications using Sysmon and Splunk while following a structured SOC investigation workflow.
