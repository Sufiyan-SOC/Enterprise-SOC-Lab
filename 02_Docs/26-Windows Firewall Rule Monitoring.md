# Day 26 – Windows Firewall Rule Monitoring

## Overview

This lab focuses on monitoring Windows Firewall configuration changes using PowerShell and Splunk Enterprise. Firewall rule creation is an important security event because attackers often modify firewall rules to allow unauthorized inbound or outbound communication.

The objective of this exercise was to create a temporary firewall rule, verify its creation, investigate the activity in Splunk, and understand how firewall configuration changes can be detected and investigated.

---

## Objectives

* Monitor Windows Firewall rule changes.
* Detect firewall-related activity in Splunk.
* Investigate newly created firewall rules.
* Differentiate legitimate administrative changes from suspicious modifications.
* Understand how firewall rule monitoring supports endpoint security.

---

## Technologies Used

* Windows PowerShell
* Windows Defender Firewall
* Splunk Enterprise

---

## Skills Demonstrated

* Firewall monitoring
* Splunk investigation
* Threat hunting
* Endpoint security monitoring
* Administrative activity analysis

---

## Detection Workflow

1. Create a temporary firewall rule.
2. Verify the rule locally.
3. Search for related events in Splunk.
4. Determine whether the change is expected.
5. Remove the temporary rule.

---

## MITRE ATT&CK Mapping

| Technique | Description                                        |
| --------- | -------------------------------------------------- |
| T1562.004 | Impair Defenses: Disable or Modify System Firewall |

---

## Outcome

Successfully monitored a Windows Firewall rule modification, validated the event in Splunk, and learned how firewall configuration changes can indicate either legitimate administration or attacker defense evasion.
