# Detection Name

Windows Service Installation Monitoring

---

## Detection ID

DR-011

---

## Detection Purpose

Detect newly installed Windows Services that may indicate persistence or unauthorized software installation.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

T1543.003 – Create or Modify System Process: Windows Service

---

## Data Source

Windows System Log

Event ID 7045

---

## Detection Coverage

* ✔ Windows Event Logs
* ✔ Splunk
* ✔ MITRE ATT&CK
* ✔ Threat Hunting
* ✔ IOC Hunting
* ✔ Persistence Detection

---

## Detection Logic

Monitor Event ID 7045 and investigate newly installed services, especially those using suspicious names, unusual executable paths, or automatic startup.

---

## Splunk Detection Query

```spl
index=* source="WinEventLog:System" EventCode=7045
| table _time _raw
```

---

## Severity

High

---

## False Positives

* Legitimate software installation
* Windows updates
* Driver installation
* Enterprise software deployment

---

## Triage Steps

1. Review service name.
2. Verify executable path.
3. Validate startup type.
4. Check service account.
5. Correlate with Process Creation events.

---

## Recommended Analyst Actions

* Verify service legitimacy.
* Review digital signature.
* Check file location.
* Investigate persistence indicators.
* Escalate if malicious.

---

## Detection Validation

* ☑ Event Generated
* ☑ Event Received in Splunk
* ☑ Query Returned Results
* ☑ Detection Logic Verified
* ☑ False Positives Reviewed

---

## References

* MITRE ATT&CK T1543.003
* Microsoft Windows Event Documentation
