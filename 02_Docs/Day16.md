# Day 16 – PowerShell Threat Hunting

## Objective

The objective of Day 16 was to understand how PowerShell execution appears in Sysmon logs and how Security Operations Center (SOC) analysts investigate PowerShell activity using Splunk Enterprise.

The lab focused on process creation events, parent process analysis, execution trends, and basic threat hunting techniques.

---

# Lab Environment

| Component        | Details                       |
| ---------------- | ----------------------------- |
| SIEM             | Splunk Enterprise 10.4.0      |
| Operating System | Ubuntu Server 22.04.5 LTS     |
| Windows Endpoint | CLIENT1                       |
| User             | sbish                         |
| Log Source       | Microsoft Sysmon              |
| Event Used       | Event ID 1 – Process Creation |

---

# Learning Objectives

* Verify Sysmon process creation events.
* Detect PowerShell execution.
* Investigate parent-child process relationships.
* Analyze PowerShell execution trends.
* Understand how SOC analysts validate PowerShell activity.
* Build foundational PowerShell hunting skills.

---

# Activities Performed

* Verified Splunk and Sysmon log ingestion.
* Generated normal PowerShell activity.
* Investigated PowerShell Process Creation events.
* Identified the parent process responsible for launching PowerShell.
* Performed PowerShell execution trend analysis.
* Built a basic hunting workflow using Splunk SPL.

---

# Investigation Workflow

The investigation followed a structured SOC workflow:

1. Confirmed Sysmon Event ID 1 availability.
2. Identified PowerShell process execution.
3. Verified the executing user.
4. Reviewed the parent process.
5. Checked execution frequency using time-based analysis.
6. Determined whether the observed activity was normal or required further investigation.

---

# Key Findings

* PowerShell execution was successfully captured through Sysmon Event ID 1.
* The parent process observed during the investigation was **explorer.exe**, indicating interactive user activity.
* No suspicious parent processes (such as Microsoft Office applications or scripting engines) were identified.
* PowerShell execution frequency appeared consistent with expected lab activity.

---

# MITRE ATT&CK Mapping

| Technique ID | Technique  |
| ------------ | ---------- |
| T1059.001    | PowerShell |

---

# Skills Gained

* PowerShell Threat Hunting
* Sysmon Event Analysis
* Process Creation Investigation
* Parent Process Analysis
* SPL Query Development
* Time-Based Event Analysis
* SOC Investigation Workflow

---


# Challenges Encountered

During the investigation, it was observed that the current Sysmon configuration did not record complete PowerShell command-line arguments. The hunting workflow was adapted to focus on available telemetry such as **Image**, **ParentImage**, **User**, and execution frequency.

This reflects a common real-world SOC scenario where analysts must adapt detection strategies based on the available logging configuration.

---

# Outcome

Successfully investigated PowerShell execution using Sysmon Process Creation events and developed a structured hunting workflow within Splunk. The lab reinforced the importance of process context, parent-child relationships, and execution trends when validating PowerShell activity.

---
