# Day 16 – PowerShell Activity Investigation

## Objective

The objective of this lab was to understand how PowerShell execution is recorded through Microsoft Sysmon and how Splunk Enterprise can be used to investigate PowerShell process activity on Windows endpoints.

The focus was on validating process creation events, reviewing process context, analyzing parent-child relationships, and documenting the investigation workflow from a SOC analyst's perspective.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM | Splunk Enterprise 10.4.0 |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint | CLIENT1 |
| User | sbish |
| Log Source | Microsoft Sysmon |
| Event Used | Event ID 1 – Process Creation |

---

# Lab Objectives

- Validate Microsoft Sysmon Process Creation events.
- Identify PowerShell execution on the monitored endpoint.
- Analyze the parent process responsible for launching PowerShell.
- Review process execution details available in Sysmon logs.
- Understand the investigation workflow used by SOC analysts.

---

# Activities Performed

- Verified successful ingestion of Microsoft Sysmon logs into Splunk Enterprise.
- Executed PowerShell on the Windows endpoint.
- Confirmed PowerShell process creation events.
- Reviewed the associated parent process.
- Validated the executing user account.
- Documented the observed process activity.

---

# Investigation Workflow

The investigation followed the standard SOC investigation process:

1. Confirm Sysmon Event ID 1 availability.
2. Identify PowerShell process execution.
3. Verify the executing user account.
4. Review the parent process.
5. Validate the process execution context.
6. Determine whether the observed activity is expected or requires further investigation.

---

# Investigation Summary

The investigation confirmed that PowerShell execution was successfully captured through Microsoft Sysmon Process Creation events.

The parent process observed during testing was **explorer.exe**, indicating that PowerShell was launched interactively by the logged-in user.

No abnormal parent-child process relationships or unexpected execution patterns were identified during this controlled lab exercise.

---

# MITRE ATT&CK Mapping

| Technique ID | Technique |
|--------------|-----------|
| T1059.001 | PowerShell |

---

# Skills Demonstrated

- Windows Process Investigation
- Microsoft Sysmon Log Analysis
- Splunk Enterprise Investigation
- Parent Process Analysis
- Process Creation Validation
- SOC Investigation Workflow

---

# Challenges Encountered

The current Microsoft Sysmon configuration did not capture complete PowerShell command-line arguments.

As a result, the investigation focused on the available telemetry, including:

- Process Image
- Parent Process
- Executing User
- Process Creation Event

This reflects a common operational scenario where SOC analysts must perform investigations using the telemetry available within the existing logging configuration.

---

# Conclusion

This lab demonstrated how Microsoft Sysmon Process Creation events can be used within Splunk Enterprise to investigate PowerShell activity on Windows systems.

Although complete command-line visibility was not available, the investigation successfully validated process execution, execution context, and parent-child relationships using the available endpoint telemetry.
