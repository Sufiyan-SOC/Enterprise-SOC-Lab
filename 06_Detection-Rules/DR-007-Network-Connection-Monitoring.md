# Detection Name

Network Connection Monitoring

---

## Detection ID

DR-007

---

## Detection Purpose

Detect outbound network connections initiated by Windows processes to identify suspicious communication and potential command-and-control activity.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

**T1071 – Application Layer Protocol**

---

## Data Source

Microsoft Sysmon

Event ID 3 – Network Connection

---

## Detection Logic

Monitor processes establishing outbound network connections. Investigate unexpected processes, uncommon destination ports, and unknown destination IP addresses.

---

## Splunk Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| table _time Image User DestinationIp DestinationPort Protocol
```

---

## Severity

Medium

---

## False Positives

* Web browsers
* Software updates
* Enterprise applications
* Windows services

---

## Triage Steps

1. Identify the originating process.
2. Review destination IP and port.
3. Verify user context.
4. Correlate with process creation events.
5. Investigate unusual communication patterns.

---

## Recommended Analyst Actions

* Validate process legitimacy.
* Review destination reputation.
* Investigate suspicious outbound communication.
* Escalate confirmed malicious activity.

---

## References

* MITRE ATT&CK T1071
* Microsoft Sysmon Documentation
