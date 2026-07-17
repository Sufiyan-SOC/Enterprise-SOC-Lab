# Day 22 – Process Access Monitoring using Splunk & Sysmon

## Overview

This lab focuses on monitoring process-to-process access activity using **Microsoft Sysmon Event ID 10** and **Splunk Enterprise**. Process Access events help security analysts identify applications attempting to access other running processes, making this telemetry valuable for detecting credential dumping, process injection, and post-exploitation techniques.

The objective of this exercise was to generate safe process access activity, collect Sysmon telemetry, investigate Process Access events in Splunk, and understand how abnormal process interactions can indicate malicious behavior.

---

## Objectives

* Monitor Process Access events using Sysmon Event ID 10.
* Investigate process-to-process interactions in Splunk.
* Analyze source and target processes.
* Understand Granted Access permissions.
* Differentiate normal and suspicious process access activity.
* Map Process Access monitoring to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Microsoft Sysmon
* Windows Event Logs
* Windows PowerShell
* Windows Task Manager

---

## Skills Demonstrated

* Process Access monitoring
* Endpoint telemetry analysis
* Process correlation
* Splunk investigation
* IOC-based threat hunting
* MITRE ATT&CK mapping

---

## Detection Workflow

1. Generate safe process access activity.
2. Collect Sysmon Event ID 10 telemetry.
3. Ingest logs into Splunk.
4. Identify source and target processes.
5. Review Granted Access permissions.
6. Investigate abnormal process interactions.

---

## MITRE ATT&CK Mapping

| Technique | Description           |
| --------- | --------------------- |
| T1003     | OS Credential Dumping |

---

## Outcome

Successfully monitored Process Access events using Microsoft Sysmon Event ID 10 and Splunk Enterprise. The lab demonstrated how Process Access telemetry can help identify suspicious interactions between processes, support credential dumping detection, and improve endpoint visibility during security investigations.
