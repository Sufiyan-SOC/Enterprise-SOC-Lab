# Day 14 - Sysmon Process Investigation & Threat Hunting

## Objective

The objective of Day 14 was to understand how Sysmon records process creation events and how Splunk can be used to investigate process execution, parent-child relationships, and perform basic threat hunting.

---

# Lab Environment

| Component           | Details                   |
| ------------------- | ------------------------- |
| SIEM                | Splunk Enterprise 10.4.0  |
| Operating System    | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint    | CLIENT1                   |
| Windows User        | sbish                     |
| Sysmon              | Installed                 |
| Sysmon Add-on       | Installed                 |
| Universal Forwarder | Running                   |

---

# Objectives Completed

* Verified Sysmon log ingestion
* Investigated Process Creation Events (Event ID 1)
* Investigated Notepad execution
* Investigated Command Prompt execution
* Investigated PowerShell execution
* Analyzed Parent-Child Process Relationship
* Performed Basic Process Hunting
* Identified Most Executed Processes

---

# What is Sysmon?

System Monitor (Sysmon) is a Microsoft Sysinternals tool that provides detailed Windows event logging. These logs help SOC analysts detect malicious activities that are not available in standard Windows logs.

---

# Event ID Covered

| Event ID | Description      |
| -------- | ---------------- |
| 1        | Process Creation |

---

# Practical Activities

## Process Creation Investigation

The following applications were executed and monitored in Splunk:

* Notepad
* Command Prompt
* PowerShell

Each execution generated Sysmon Process Creation events.

---

# Parent-Child Process Relationship

Understanding parent-child relationships helps analysts determine how a process was launched.

Example:

```text
explorer.exe
      │
      ├── notepad.exe
      ├── cmd.exe
      └── powershell.exe
```

This represents normal user activity.

Suspicious examples include:

```text
winword.exe
      │
      └── powershell.exe
```

or

```text
excel.exe
      │
      └── cmd.exe
```

These process chains require further investigation.

---

# SPL Queries Used

## Verify Sysmon Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
```

---

## Process Creation Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
```

---

## Notepad Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" notepad.exe
```

---

## Command Prompt Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" cmd.exe
```

---

## PowerShell Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" powershell.exe
```

---

## Process Hunting

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
(Image="*cmd.exe" OR Image="*powershell.exe")
| table _time Image ParentImage CommandLine User Computer
```

---

## Process Execution Statistics

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
| stats count by Image
| sort -count
```

---

# Skills Learned

* Sysmon Event Analysis
* Process Creation Monitoring
* Parent-Child Process Analysis
* Process Hunting
* PowerShell Monitoring
* Command Prompt Investigation
* Windows Process Investigation
* Basic Threat Hunting using Splunk

---

# Challenges Faced

* Initially, EventID fields were not extracted because the Sysmon Add-on was not installed.
* After installing the Sysmon Add-on, Splunk successfully parsed EventID fields, allowing more accurate searches and investigations.
* ParentImage fields became available after proper field extraction.

---

# Outcome

Successfully investigated Windows process creation events using Sysmon and Splunk.

The lab can now:

* Detect newly created processes
* Track PowerShell execution
* Track Command Prompt execution
* Monitor application launches
* Identify parent-child process relationships
* Perform basic process hunting using SPL

---

# Key Takeaways

* Event ID 1 records every process creation.
* ParentImage is critical for understanding how a process was launched.
* PowerShell and CMD should always be monitored because they are commonly abused by attackers.
* Sysmon provides significantly more visibility than standard Windows Event Logs.
* Splunk SPL can be used to investigate process execution efficiently.

---


