# Hunt Name

Windows Service Persistence Hunting

---

## Hunt ID

TH-011

---

## Objective

Identify unauthorized Windows Service installations that may indicate persistence.

---

## Threat Hypothesis

An attacker may install a malicious Windows Service to maintain persistence after initial access.

---

## Required Data Sources

* Windows System Logs
* Event ID 7045

---

## MITRE ATT&CK

T1543.003 – Create or Modify System Process: Windows Service

---

## Hunt Procedure

1. Review Event ID 7045.
2. Identify newly installed services.
3. Verify executable paths.
4. Check startup configuration.
5. Validate service legitimacy.

---

## Hunt Query

```spl
index=* source="WinEventLog:System" EventCode=7045
| table _time _raw
```

---

## Expected Findings

* Newly installed services
* Administrative software installation
* Windows updates
* Enterprise software deployment

---

## IOC Examples

* Service names mimicking Microsoft.
* Executables in Temp or Public folders.
* Automatic startup for unknown services.
* Randomly named services.

---

## Expected Analyst Outcome

The analyst should be able to:

* Identify suspicious service installations.
* Validate service configuration.
* Detect persistence techniques.
* Determine whether escalation is required.

---

## Investigation Guidance

Correlate Event ID 7045 with Process Creation (Event ID 1), Registry Events, and File Creation events to determine how the service was installed and whether it represents malicious persistence.

---

## References

* MITRE ATT&CK T1543.003
* Microsoft Windows Documentation
