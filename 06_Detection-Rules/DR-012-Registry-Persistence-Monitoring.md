# Detection Name

Registry Persistence Monitoring

---

## Detection ID

DR-012

---

## Detection Purpose

Detect Registry Run Key modifications that may indicate persistence or unauthorized system configuration changes.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder

---

## Data Source

Microsoft Sysmon

Event ID 13 – Registry Value Set

---

## Detection Coverage

* ✔ Sysmon
* ✔ Splunk
* ✔ MITRE ATT&CK
* ✔ Threat Hunting
* ✔ Persistence Detection

---

## Detection Logic

Monitor Registry Value Set events and investigate modifications made to Windows Run Keys or other persistence-related registry locations.

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=13
| table _time _raw
```

---

## Severity

High

---

## False Positives

* Software installation
* Windows updates
* Legitimate application configuration
* Administrative changes

---

## Triage Steps

1. Identify the modifying process.
2. Review the registry path.
3. Verify the configured executable.
4. Correlate with Process Creation (Event ID 1).
5. Validate whether the change is expected.

---

## Recommended Analyst Actions

* Verify executable legitimacy.
* Review digital signature.
* Check startup behavior.
* Investigate persistence indicators.
* Escalate suspicious registry changes.

---

## Detection Validation

* ☑ Event Generated
* ☑ Event Received in Splunk
* ☑ Query Returned Results
* ☑ Detection Logic Verified
* ☑ False Positives Reviewed

---

## References

* MITRE ATT&CK T1547.001
* Microsoft Sysmon Documentation
