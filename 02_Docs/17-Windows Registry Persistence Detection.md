# Day 17 – Windows Registry Persistence Detection

## Overview

This lab focused on detecting Windows Registry Run Key persistence using Microsoft Sysmon and Splunk Enterprise.

Windows Registry Run and RunOnce keys are commonly used by legitimate software to launch applications automatically during user logon. The same mechanism is frequently abused by attackers to establish persistence after compromising a system.

The objective of this exercise was to detect Registry modifications, investigate the associated process activity, validate whether the behavior was expected, and document the findings using a standard SOC investigation workflow.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM | Splunk Enterprise 10.4.0 |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint | CLIENT1 |
| User | sbish |
| Log Source | Microsoft Sysmon |
| Event ID | 13 (Registry Value Set) |

---

# Objectives

- Understand Windows Registry Run Key persistence.
- Monitor Registry modifications using Microsoft Sysmon.
- Detect Registry Run and RunOnce changes in Splunk.
- Investigate Registry persistence activity using structured analysis.
- Develop detection logic for Registry-based persistence.
- Map the activity to the MITRE ATT&CK framework.

---

# Lab Activities

During this exercise, the following tasks were completed:

- Verified Microsoft Sysmon Registry logging.
- Created a controlled Registry Run Key for testing.
- Collected Registry events in Splunk.
- Investigated Registry modification activity.
- Validated the process responsible for the Registry change.
- Reviewed Registry value data and execution context.
- Removed the test Registry entry after validation.

---

# Investigation Workflow

The investigation followed a structured SOC workflow:

1. Validate Registry modification events.
2. Identify the affected Registry path.
3. Review the process responsible for the modification.
4. Examine the Registry value and associated executable.
5. Determine whether the activity represents legitimate software or persistence.
6. Document the investigation findings.

---

# Key Findings

The investigation confirmed the following:

- Registry Run Key activity was successfully logged by Microsoft Sysmon Event ID 13.
- The modification occurred within a Windows autorun Registry location.
- The Registry value was created using **reg.exe**.
- The configured executable was **Notepad**, representing controlled laboratory activity.
- No unauthorized persistence or suspicious executable was identified during the investigation.

---

# Detection Strategy

The detection focuses on monitoring Registry autorun locations commonly targeted for persistence, including:

- HKCU\Software\Microsoft\Windows\CurrentVersion\Run
- HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce
- HKLM\Software\Microsoft\Windows\CurrentVersion\Run
- HKLM\Software\Microsoft\Windows\CurrentVersion\RunOnce

When Registry modifications occur within these locations, analysts should validate:

- Registry path
- Modified value
- Executing process
- User account
- Associated executable
- Execution context

This approach helps distinguish legitimate software installation from potential persistence techniques.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Persistence | Registry Run Keys / Startup Folder | T1547.001 |

---

# Skills Demonstrated

- Windows Registry Analysis
- Microsoft Sysmon Log Analysis
- Splunk Detection Engineering
- Windows Persistence Detection
- Event Correlation
- SOC Investigation Workflow
- MITRE ATT&CK Mapping
- Incident Documentation

---

# Challenges

Registry Run Keys are frequently modified by legitimate applications during software installation and system updates.

Because of this, Registry modifications alone should not be treated as malicious. Accurate analysis requires reviewing the Registry path, responsible process, configured executable, and overall system context before determining whether the activity represents persistence.

---

# Outcome

Successfully detected and investigated Windows Registry Run Key activity using Microsoft Sysmon and Splunk Enterprise.

This exercise demonstrated how Registry persistence can be identified through endpoint telemetry and highlighted the importance of contextual analysis when investigating Windows autorun mechanisms in a Security Operations Center (SOC) environment.
