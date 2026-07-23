# Day 23 – Windows Service Installation Monitoring

## Overview

This lab demonstrates how Windows Service installation events can be monitored using **Windows Event ID 7045** and **Splunk Enterprise**.

Windows Services are widely used by administrators to install and manage applications. However, attackers also abuse Windows Services to establish persistence and execute malicious programs with elevated privileges.

The purpose of this lab was to generate a legitimate service installation event, collect the corresponding Windows logs in Splunk, and analyze the activity from a Security Operations Center (SOC) perspective.

---

## Objectives

- Monitor Windows Service installation events.
- Detect Windows Event ID 7045 in Splunk Enterprise.
- Identify newly installed Windows Services.
- Investigate service installation activity.
- Understand how Windows Services can be abused for persistence.
- Map the detection to the MITRE ATT&CK framework.

---

## Technologies Used

- Windows Server 2022
- Windows 11 Enterprise
- Splunk Enterprise
- Windows Event Logs
- Service Control Manager (SCM)

---

## Skills Demonstrated

- Windows Event Log Analysis
- Splunk Detection Engineering
- Security Event Investigation
- Windows Persistence Monitoring
- MITRE ATT&CK Mapping
- SOC Alert Analysis

---

## Detection Workflow

1. Generate a Windows Service installation event.
2. Collect Windows Security logs in Splunk.
3. Detect Event ID 7045.
4. Review service installation details.
5. Validate whether the service is authorized.
6. Document the findings.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Persistence | Create or Modify System Process: Windows Service | T1543.003 |

---

## Outcome

Splunk Enterprise successfully detected Windows Service installation events generated during the lab. The collected telemetry provided sufficient information to identify the installed service, support analyst investigation, and demonstrate how Windows Service creation can be monitored as a potential persistence technique in an enterprise environment.
