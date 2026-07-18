# Day 25 – Windows Account Management Monitoring using Splunk

## Overview

This lab focuses on monitoring Windows user account management events using Windows Security Logs and Splunk Enterprise. User account creation, deletion, password resets, and group membership changes are critical security events that may indicate administrative activity or attacker persistence.

The objective of this exercise was to create a temporary lab user account, generate Security Event ID 4720, investigate the event in Splunk, and understand how account management events support threat detection and incident response.

---

## Objectives

* Monitor Windows Account Management events.
* Detect Security Event ID 4720 in Splunk.
* Investigate newly created user accounts.
* Differentiate legitimate administrative activity from suspicious account creation.
* Map account management activity to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Windows Security Logs
* Windows PowerShell
* Windows User Management

---

## Skills Demonstrated

* Windows Account Monitoring
* Splunk Investigation
* Threat Hunting
* Insider Threat Detection
* MITRE ATT&CK Mapping

---

## Detection Workflow

1. Create a temporary lab user.
2. Generate Security Event ID 4720.
3. Collect the event in Splunk.
4. Investigate the account creation.
5. Validate whether the activity is legitimate.
6. Remove the lab account.

---

## MITRE ATT&CK Mapping

| Technique | Description          |
| --------- | -------------------- |
| T1098     | Account Manipulation |
| T1078     | Valid Accounts       |

---

## Outcome

Successfully detected Windows user account creation using Security Event ID 4720. The exercise demonstrated how Security Event Logs can be used to monitor administrative activity and detect unauthorized account creation.
