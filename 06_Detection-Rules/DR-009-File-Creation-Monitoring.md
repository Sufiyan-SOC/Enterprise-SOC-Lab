# Detection Name

File Creation Monitoring

---

## Detection ID

DR-009

---

## Detection Purpose

Detect newly created files that may indicate malware payload delivery, unauthorized executables, or suspicious script creation.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

T1105 – Ingress Tool Transfer

---

## Data Source

Microsoft Sysmon

Event ID 11 – File Create

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

Monitor newly created files and identify suspicious file paths, executable drops, PowerShell-created files, and abnormal file creation behavior.

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11
| table _time Image TargetFilename User
```

---

## Severity

Medium

---

## False Positives

* Software installation
* Windows updates
* Application updates
* User-created files

---

## Triage Steps

1. Identify the creating process.
2. Review the file path.
3. Determine file type.
4. Correlate with Process Creation (Event ID 1).
5. Correlate with Network Connections (Event ID 3).

---

## Recommended Analyst Actions

* Validate file legitimacy.
* Review parent process.
* Check digital signature.
* Calculate file hash.
* Escalate if suspicious.

---

## References

* MITRE ATT&CK T1105
* Microsoft Sysmon Documentation
