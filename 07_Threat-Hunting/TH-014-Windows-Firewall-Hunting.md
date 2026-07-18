# Hunt Name

Windows Firewall Rule Hunting

---

## Hunt ID

TH-014

---

## Objective

Identify unauthorized Windows Firewall rule creation that may expose systems to remote access or weaken endpoint protection.

---

## Threat Hypothesis

An attacker may create or modify Windows Firewall rules to allow malicious inbound connections or bypass security controls.

---

## Required Data Sources

* Windows Firewall
* Splunk

---

## MITRE ATT&CK

T1562.004 – Impair Defenses: Disable or Modify System Firewall

---

## Hunt Query

```spl
index=* Firewall
```

---

## Normal Output

* Temporary administrative firewall rule.
* Known port.
* Approved change.
* Documented activity.

---

## Suspicious Output

* Unknown firewall rule.
* Uncommon open port.
* Fake Microsoft rule names.
* Unexpected inbound allow rules.

---

## IOC Examples

* Port 4444
* Port 1337
* Random high ports
* Rules created immediately after suspicious PowerShell execution
* Multiple firewall modifications within a short time

---

## Analyst Outcome

The analyst should determine whether the firewall change is authorized, identify the associated process or administrator, review exposed ports, and assess whether the modification could enable unauthorized remote access.

---

## Investigation Guidance

Correlate firewall activity with:

* Process Creation
* Network Connections
* User Logon Events
* Service Installation

to understand the complete activity timeline.

---

## References

* MITRE ATT&CK T1562.004
* Microsoft Windows Defender Firewall Documentation
