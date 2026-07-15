# Hunt Name

Network Connection Hunting

---

## Hunt ID

TH-007

---

## Objective

Identify suspicious outbound network communication initiated by Windows processes.

---

## Threat Hypothesis

An attacker may establish outbound communication with external infrastructure after gaining access to a Windows endpoint.

---

## Pre-Requisites

* Microsoft Sysmon installed
* Event ID 3 enabled
* Splunk ingesting Sysmon logs

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 3

---

## MITRE ATT&CK

T1071 – Application Layer Protocol

---

## Hunt Procedure

1. Review all network connection events.
2. Identify processes generating outbound traffic.
3. Analyze destination IP addresses.
4. Review destination ports.
5. Correlate with process creation events.
6. Validate user activity.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| table _time Image User DestinationIp DestinationPort Protocol
```

---

## Expected Findings

* Process-to-network relationships
* Destination IP addresses
* Destination ports
* Network communication timeline

---

## IOC Examples

* Unknown external IP addresses
* PowerShell initiating network connections
* Communication over uncommon ports
* Repeated connections to a single external host

---

## Investigation Guidance

Correlate network activity with process creation, PowerShell execution, Registry modifications, and Scheduled Task events to determine whether the communication is legitimate or indicative of post-exploitation.

---

## References

* MITRE ATT&CK T1071
* Microsoft Sysmon Documentation
