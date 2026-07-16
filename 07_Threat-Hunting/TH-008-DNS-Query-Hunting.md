# Hunt Name

DNS Query Hunting

---

## Hunt ID

TH-008

---

## Objective

Identify suspicious DNS queries initiated by Windows processes.

---

## Threat Hypothesis

An attacker may use DNS to resolve command-and-control infrastructure, malware hosting domains, or phishing websites before establishing outbound communication.

---

## Pre-Requisites

* Microsoft Sysmon installed
* Event ID 22 enabled
* Splunk receiving Sysmon logs

---

## Required Data Sources

* Microsoft Sysmon
* Event ID 22

---

## MITRE ATT&CK

T1071.004 – DNS

---

## Hunt Procedure

1. Review DNS query events.
2. Identify querying processes.
3. Review queried domains.
4. Validate DNS responses.
5. Correlate with network connections and process creation events.

---

## Hunt Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=22
| table _time Image User QueryName QueryResults
```

---

## Expected Findings

* Process-to-domain relationships
* Frequently queried domains
* DNS resolution history
* User activity

---

## IOC Examples

* Newly registered domains
* Dynamic DNS providers
* Random-looking domain names
* PowerShell resolving external domains

---

## Investigation Guidance

Correlate DNS activity with Sysmon Event ID 3 (Network Connections), Event ID 1 (Process Creation), and endpoint behavior before determining malicious activity.

---

## References

* MITRE ATT&CK T1071.004
* Microsoft Sysmon Documentation
