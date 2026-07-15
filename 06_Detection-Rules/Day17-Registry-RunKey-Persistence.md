# Registry Run Key Persistence Detection

## Objective

Detect Registry Run Key persistence using Microsoft Sysmon Event ID 13.

---

## Data Source

Microsoft Sysmon

Event ID 13

---

## Detection Strategy

Monitor modifications to:

* CurrentVersion\Run
* CurrentVersion\RunOnce

Validate:

* Registry path
* Executing process
* User
* Registry value

---

## False Positives

* Software installation
* Legitimate application startup entries
* Enterprise software deployment

---

## Severity

High

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder
