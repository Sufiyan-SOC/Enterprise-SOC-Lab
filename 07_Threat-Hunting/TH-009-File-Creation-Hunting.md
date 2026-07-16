# Hunt Name

File Creation Hunting

---

## Hunt ID

TH-009

---

## Objective

Identify suspicious file creation activity that may indicate malware delivery or post-exploitation.

---

## Threat Hypothesis

An attacker may create executable files or scripts on a compromised endpoint to establish persistence or execute malicious payloads.

---

## Pre-Requisites

* Microsoft Sysmon installed
* Event ID 11 enabled
* Splunk ingesting Sysmon logs

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 11

---

## MITRE ATT&CK

T1105 – Ingress Tool Transfer

---

## Hunt Procedure

1. Review newly created files.
2. Identify the creating process.
3. Investigate suspicious directories.
4. Correlate with Process Creation and Network Connection events.
5. Validate file legitimacy.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11
| table _time Image User TargetFilename
```

---

## Expected Findings

* New executable files
* PowerShell-generated files
* Files created in unusual locations
* Suspicious file paths

---

## IOC Examples

* Executables in Temp or Public folders
* Unexpected PowerShell script creation
* Payloads dropped outside standard application directories
* Randomly named executable files

---

## Expected Analyst Outcome

The analyst should be able to:

* Identify suspicious file creation events.
* Validate the creating process.
* Correlate file activity with endpoint telemetry.
* Determine whether escalation is required.

---

## Investigation Guidance

Correlate Event ID 11 with Process Creation (Event ID 1), Network Connections (Event ID 3), and DNS Queries (Event ID 22) to understand the complete attack sequence.

---

## References

* MITRE ATT&CK T1105
* Microsoft Sysmon Documentation
