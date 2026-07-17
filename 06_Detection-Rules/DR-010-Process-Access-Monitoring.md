# Detection Name

Process Access Monitoring

---

## Detection ID

DR-010

---

## Detection Purpose

Detect suspicious process-to-process access activity that may indicate credential dumping, process injection, or post-exploitation techniques.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

T1003 – OS Credential Dumping

---

## Data Source

Microsoft Sysmon

Event ID 10 – Process Access

---

## Detection Coverage

* ✔ Sysmon
* ✔ Splunk
* ✔ MITRE ATT&CK
* ✔ Threat Hunting
* ✔ IOC Hunting
* ✔ Incident Investigation

---

## Detection Logic

Monitor processes accessing other running processes, especially high-value targets such as **lsass.exe**, **winlogon.exe**, and **services.exe**. Investigate unusual source processes, unexpected access permissions, and abnormal process relationships.

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=10
| table _time SourceImage TargetImage GrantedAccess User
```

---

## Severity

High

---

## False Positives

* Antivirus software
* Endpoint security tools
* Task Manager
* Process Explorer
* Administrative troubleshooting tools

---

## Triage Steps

1. Identify the source process.
2. Verify the target process.
3. Review Granted Access permissions.
4. Correlate with Process Creation (Event ID 1).
5. Review Network Connections (Event ID 3).

---

## Recommended Analyst Actions

* Validate process legitimacy.
* Review digital signatures.
* Investigate unexpected LSASS access.
* Correlate with endpoint telemetry.
* Escalate confirmed suspicious activity.

---

## References

* MITRE ATT&CK T1003
* Microsoft Sysmon Documentation
