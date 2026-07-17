# Day 23 – Windows Service Installation Monitoring using Splunk

## Overview

This lab focuses on monitoring Windows Service installation events using **Windows Event ID 7045** and **Splunk Enterprise**. Windows Services are commonly used by administrators for legitimate software installations, but they are also a well-known persistence mechanism used by attackers.

The objective of this exercise was to create a safe Windows service, collect Event ID 7045 logs, investigate the activity in Splunk, and understand how service installation events can be used to detect persistence techniques.

---

## Objectives

* Monitor Windows Service installation events.
* Detect Event ID 7045 in Splunk.
* Investigate newly installed services.
* Differentiate normal and suspicious service installations.
* Map service persistence to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Windows Event Logs
* Windows PowerShell
* Service Control (sc.exe)

---

## Skills Demonstrated

* Windows Service Monitoring
* Persistence Detection
* Splunk Investigation
* IOC-based Threat Hunting
* MITRE ATT&CK Mapping

---

## Detection Workflow

1. Create a safe Windows service.
2. Generate Event ID 7045.
3. Ingest logs into Splunk.
4. Investigate the service installation.
5. Identify indicators of persistence.
6. Validate whether the service is legitimate.

---

## MITRE ATT&CK Mapping

| Technique | Description                                      |
| --------- | ------------------------------------------------ |
| T1543.003 | Create or Modify System Process: Windows Service |

---

## Outcome

Successfully detected Windows Service installation events using Event ID 7045 and Splunk Enterprise. The lab demonstrated how service creation can be monitored to identify persistence techniques and support endpoint investigations.
