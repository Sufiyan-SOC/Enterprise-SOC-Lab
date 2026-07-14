# Incident Report

## Incident Title

PowerShell Execution Investigation

---

## Summary

PowerShell execution events were investigated using Microsoft Sysmon process creation logs. The analysis focused on identifying the executing user, reviewing the parent process, and validating whether the activity represented legitimate administrative usage.

---

## Data Source

Microsoft Sysmon

Process Creation Events

---

## Investigation Findings

* PowerShell execution was successfully detected.
* The responsible user account was identified.
* Parent process relationships were reviewed.
* Timeline analysis confirmed expected laboratory activity.
* No malicious PowerShell execution was identified.

---

## Severity

Low

Controlled Laboratory Activity

---

## MITRE ATT&CK

T1059.001 – PowerShell

---

## Analyst Conclusion

PowerShell execution matched expected laboratory activity. The investigation demonstrated the ability to detect, validate, and analyze PowerShell execution using Sysmon and Splunk while following a structured SOC investigation workflow.
