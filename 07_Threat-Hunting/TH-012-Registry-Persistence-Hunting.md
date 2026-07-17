# Hunt Name

Registry Persistence Hunting

---

## Hunt ID

TH-012

---

## Objective

Identify Registry Run Key modifications that could indicate persistence on Windows endpoints.

---

## Threat Hypothesis

An attacker may modify Windows Registry Run Keys to automatically execute malicious software after user logon.

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 13

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder

---

## Hunt Procedure

1. Review Registry Value Set events.
2. Identify modified registry paths.
3. Verify associated executables.
4. Correlate with Process Creation events.
5. Determine whether persistence was established.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=13
| table _time _raw
```

---

## Expected Findings

* Administrative registry changes
* Software installation activity
* Startup configuration updates
* Registry persistence attempts

---

## IOC Examples

* Run Key pointing to executables in Temp or Public folders.
* Unknown executables configured for startup.
* PowerShell modifying startup registry keys.
* Suspicious registry changes outside normal administration.

---

## Expected Analyst Outcome

The analyst should be able to identify registry persistence techniques, validate registry modifications, correlate related endpoint telemetry, and determine whether escalation is required.

---

## Investigation Guidance

Correlate Registry Value Set events with Process Creation (Event ID 1), File Creation (Event ID 11), Network Connections (Event ID 3), and DNS Queries (Event ID 22) to understand the complete attack chain.

---

## References

* MITRE ATT&CK T1547.001
* Microsoft Sysmon Documentation
