# Day 21 – File Creation Monitoring using Splunk & Sysmon

## Overview

This lab focuses on monitoring file creation activity using **Microsoft Sysmon Event ID 11** and **Splunk Enterprise**. File creation monitoring is an important endpoint detection capability because attackers frequently create or drop payloads, scripts, and executables during post-exploitation.

The objective of this exercise was to simulate file creation, collect telemetry through Sysmon, investigate the activity in Splunk, and identify indicators that differentiate normal behavior from suspicious file creation.

---

## Objectives

* Monitor Windows file creation events.
* Detect newly created files using Sysmon Event ID 11.
* Investigate file creation activity in Splunk.
* Differentiate normal and suspicious file creation patterns.
* Map file creation activity to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Microsoft Sysmon
* Windows Event Logs
* Windows PowerShell

---

## Skills Demonstrated

* File creation monitoring
* Endpoint telemetry analysis
* Splunk investigation
* IOC-based hunting
* Detection engineering
* MITRE ATT&CK mapping

---

## Detection Workflow

1. Create files within a controlled lab environment.
2. Collect Sysmon Event ID 11 logs.
3. Ingest telemetry into Splunk.
4. Investigate file creation events.
5. Identify suspicious file locations and processes.
6. Correlate findings with additional endpoint activity.

---

## MITRE ATT&CK Mapping

| Technique | Description           |
| --------- | --------------------- |
| T1105     | Ingress Tool Transfer |

---

## Outcome

Successfully monitored Windows file creation events using Microsoft Sysmon and Splunk. The lab demonstrated how file creation telemetry can be used to detect dropped payloads, identify suspicious file locations, and support endpoint investigations through process and file correlation.
