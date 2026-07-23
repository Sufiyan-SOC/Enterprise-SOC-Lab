# Day 18 – Scheduled Task Persistence Detection using Splunk & Sysmon

## Overview

This lab focuses on detecting **Windows Scheduled Task persistence** using **Microsoft Sysmon** and **Splunk**. Scheduled Tasks are a common persistence mechanism that allows programs or scripts to execute automatically based on predefined triggers such as system startup, user logon, or scheduled intervals.

The objective of this exercise was to monitor Scheduled Task creation events, analyze process execution, and investigate task creation using Splunk search queries.

---

## Objectives

* Understand Scheduled Task persistence techniques.
* Detect execution of **schtasks.exe** using Sysmon Process Creation events.
* Investigate task creation activity in Splunk.
* Analyze process relationships using **ParentImage** and **CommandLine**.
* Map Scheduled Task persistence to the MITRE ATT&CK framework.

---

## Technologies Used

* Splunk Enterprise
* Microsoft Sysmon
* Windows Event Logs
* Windows Task Scheduler

---

## Skills Demonstrated

* Windows endpoint monitoring
* Splunk log analysis
* Process creation investigation
* Scheduled Task persistence detection
* Parent-child process analysis
* MITRE ATT&CK mapping

---

## Detection Workflow

1. Create a Scheduled Task on the Windows endpoint.
2. Collect process creation events through Sysmon.
3. Ingest logs into Splunk.
4. Search for **schtasks.exe** execution.
5. Review the executing user, parent process, and command-line arguments.
6. Validate whether the activity is legitimate or suspicious.

---

## MITRE ATT&CK Mapping

| Technique | Description          |
| --------- | -------------------- |
| T1053.005 | Scheduled Task / Job |

---

## Outcome

Successfully detected Scheduled Task creation using Microsoft Sysmon and Splunk. The lab demonstrated how Scheduled Tasks can be monitored as a persistence mechanism by analyzing process creation events, parent-child relationships, and execution details. This exercise strengthened practical skills in Windows endpoint monitoring, persistence detection, and SOC investigation workflows.
