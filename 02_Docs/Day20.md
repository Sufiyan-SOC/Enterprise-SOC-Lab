# Day 20 – DNS Query Monitoring using Splunk & Sysmon

## Overview

This lab focuses on monitoring and investigating DNS queries using **Microsoft Sysmon Event ID 22** and **Splunk Enterprise**. DNS telemetry provides visibility into domain resolution requests initiated by Windows processes and helps analysts identify suspicious domains, command-and-control (C2) communication, phishing infrastructure, and abnormal endpoint behavior.

The objective of this exercise was to generate DNS activity in a controlled lab environment, collect Sysmon telemetry, investigate DNS events in Splunk, and perform basic IOC-based DNS hunting.

---

## Objectives

* Monitor DNS query events using Sysmon Event ID 22.
* Investigate DNS activity in Splunk.
* Identify processes performing DNS lookups.
* Analyze queried domains and DNS responses.
* Perform IOC-based DNS hunting.
* Map DNS monitoring to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Microsoft Sysmon
* Windows Event Logs
* Windows PowerShell

---

## Skills Demonstrated

* DNS monitoring
* Endpoint telemetry analysis
* Process-to-domain correlation
* Splunk investigation
* IOC-based threat hunting
* MITRE ATT&CK mapping

---

## Detection Workflow

1. Generate DNS queries from Windows.
2. Collect Sysmon Event ID 22 telemetry.
3. Ingest DNS events into Splunk.
4. Identify processes performing DNS queries.
5. Review queried domains and resolved IP addresses.
6. Investigate suspicious DNS activity using IOC-based hunting techniques.

---

## MITRE ATT&CK Mapping

| Technique | Description |
| --------- | ----------- |
| T1071.004 | DNS         |

---

## Outcome

Successfully monitored DNS query activity using Microsoft Sysmon Event ID 22 and Splunk Enterprise. The lab demonstrated how to identify Windows processes performing DNS lookups, investigate queried domains, review DNS resolution results, and perform basic DNS-focused threat hunting to support endpoint investigations.

