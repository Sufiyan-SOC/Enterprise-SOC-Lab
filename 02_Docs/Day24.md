# Day 24 – Registry Persistence Monitoring using Splunk & Sysmon

## Overview

This lab focuses on monitoring Windows Registry modifications using **Microsoft Sysmon Event ID 13**. Registry Run Keys are a common persistence mechanism used by attackers to automatically execute programs after user logon.

The objective of this exercise was to create a safe registry Run Key, collect Sysmon Event ID 13 telemetry, investigate registry modifications in Splunk, and understand how registry-based persistence can be detected during security investigations.

---

## Objectives

* Monitor Registry Value Set events using Sysmon Event ID 13.
* Detect Registry Run Key modifications in Splunk.
* Investigate registry persistence activity.
* Differentiate legitimate and suspicious registry modifications.
* Map registry persistence to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Microsoft Sysmon
* Windows Registry
* Windows PowerShell

---

## Skills Demonstrated

* Registry monitoring
* Persistence detection
* Splunk investigation
* Endpoint telemetry analysis
* Threat hunting
* MITRE ATT&CK mapping

---

## Detection Workflow

1. Create a safe Registry Run Key.
2. Generate Sysmon Event ID 13.
3. Ingest logs into Splunk.
4. Investigate registry modification events.
5. Identify persistence indicators.
6. Validate whether the modification is legitimate.

---

## MITRE ATT&CK Mapping

| Technique | Description                        |
| --------- | ---------------------------------- |
| T1547.001 | Registry Run Keys / Startup Folder |

---

## Outcome

Successfully monitored Registry Value Set events using Sysmon Event ID 13 and Splunk Enterprise. The lab demonstrated how registry modifications can be used to detect persistence techniques and improve endpoint visibility during investigations.
