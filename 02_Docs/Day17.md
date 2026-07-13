# Day 17 – Windows Registry Persistence Hunting

## Objective

The objective of Day 17 was to understand how attackers achieve persistence using Windows Registry Run Keys and how Security Operations Center (SOC) analysts detect and investigate Registry-based persistence using Splunk and Sysmon.

This lab focused on identifying Registry modifications, analyzing persistence artifacts, developing detection logic, and validating Registry changes through structured investigations.

---

# Lab Environment

| Component        | Details                          |
| ---------------- | -------------------------------- |
| SIEM             | Splunk Enterprise 10.4.0         |
| Operating System | Ubuntu Server 22.04.5 LTS        |
| Windows Endpoint | CLIENT1                          |
| User             | sbish                            |
| Log Source       | Microsoft Sysmon                 |
| Event Used       | Event ID 13 – Registry Value Set |

---

# Learning Objectives

* Understand Windows Registry persistence techniques.
* Detect Registry Value Set events using Sysmon.
* Identify Registry Run and RunOnce persistence locations.
* Investigate Registry modifications using Splunk SPL.
* Build a reusable Registry persistence detection rule.
* Perform timeline analysis of Registry events.
* Apply SOC investigation methodology to Registry-based persistence.

---

# Activities Performed

* Verified Sysmon Registry Event ID 13 logging.
* Created a Registry Run Key using a controlled lab artifact.
* Investigated Registry modification events in Splunk.
* Analyzed Registry paths and stored values.
* Developed a generic detection query for Registry Run and RunOnce persistence.
* Built a chronological timeline of Registry activity.
* Removed the test Registry entry to restore the lab environment.

---

# Investigation Workflow

The Registry persistence investigation followed a structured SOC workflow:

1. Verified Registry Value Set events.
2. Identified the modified Registry path.
3. Validated the process responsible for the modification.
4. Reviewed the Registry value data.
5. Determined whether the Registry entry represented legitimate activity or persistence.
6. Correlated Registry events using timeline analysis.

---

# Key Findings

* Registry Run Key creation was successfully detected using Sysmon Event ID 13.
* The Registry modification occurred under a standard Windows autorun location.
* The responsible process was **reg.exe**.
* The stored executable referenced **Notepad**, which represented expected laboratory activity.
* No malicious executables or suspicious file locations were identified during the investigation.

---

# MITRE ATT&CK Mapping

| Technique ID | Technique                          |
| ------------ | ---------------------------------- |
| T1547.001    | Registry Run Keys / Startup Folder |

---

# Detection Logic

The primary detection strategy focused on monitoring Registry modifications within Windows autorun locations, specifically:

* CurrentVersion\Run
* CurrentVersion\RunOnce

The investigation validated:

* Registry path
* Executing process
* User account
* Registry value data
* Execution timeline

This approach helps identify persistence attempts while reducing false positives through contextual analysis.

---

# Skills Gained

* Windows Registry Analysis
* Registry Persistence Hunting
* Sysmon Event ID 13 Investigation
* Registry Run Key Detection
* Splunk Search Processing Language (SPL)
* Timeline-Based Event Analysis
* Detection Engineering Fundamentals
* MITRE ATT&CK Mapping
* SOC Investigation Workflow

---

# Challenges Encountered

The investigation highlighted the importance of validating Registry modifications within their operational context. Since legitimate applications also create Run Key entries, simply detecting Registry changes is insufficient. Accurate analysis requires reviewing the Registry path, associated executable, responsible process, and overall execution context before determining whether persistence is malicious.

---

# Outcome

Successfully detected, investigated, and analyzed Windows Registry Run Key persistence using Splunk and Sysmon. The lab demonstrated how Registry autorun locations can be monitored for persistence techniques and reinforced the importance of contextual analysis when investigating Registry modifications within a SOC environment.
