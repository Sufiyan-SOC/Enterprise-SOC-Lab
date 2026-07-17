# Hunt Name

Process Access Hunting

---

## Hunt ID

TH-010

---

## Objective

Identify suspicious process-to-process access activity that could indicate credential dumping or process injection.

---

## Threat Hypothesis

An attacker may access sensitive Windows processes to extract credentials, inject malicious code, or perform post-exploitation actions.

---

## Pre-Requisites

* Microsoft Sysmon installed
* Event ID 10 enabled
* Splunk ingesting Sysmon logs

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 10

---

## MITRE ATT&CK

T1003 – OS Credential Dumping

---

## Hunt Procedure

1. Review Process Access events.
2. Identify source and target processes.
3. Analyze Granted Access permissions.
4. Correlate with Process Creation and Network Connection events.
5. Validate whether access is expected.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=10
| table _time SourceImage TargetImage GrantedAccess User
```

---

## Expected Findings

* Administrative process access
* Security software activity
* Process monitoring tools
* Unusual access to sensitive processes

---

## IOC Examples

* Unknown process accessing lsass.exe
* PowerShell accessing sensitive processes
* High privilege Granted Access values
* Multiple repeated access attempts

---

## Expected Analyst Outcome

The analyst should be able to:

* Identify abnormal process access.
* Determine whether the source process is legitimate.
* Correlate with endpoint telemetry.
* Escalate suspicious credential access attempts.

---

## Investigation Guidance

Correlate Event ID 10 with Process Creation (Event ID 1), Network Connections (Event ID 3), DNS Queries (Event ID 22), and File Creation (Event ID 11) to understand the full attack chain.

---

## References

* MITRE ATT&CK T1003
* Microsoft Sysmon Documentation
