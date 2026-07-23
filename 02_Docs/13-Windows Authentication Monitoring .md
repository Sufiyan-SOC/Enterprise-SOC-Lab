# Day 13 - Windows Authentication Monitoring 

# Overview

On Day 13, the focus was on monitoring Windows authentication events using Splunk Enterprise. Windows Security logs were analyzed to understand user authentication behavior, identify failed login attempts, and build a basic detection for brute-force activity.

This exercise introduced one of the most common monitoring responsibilities performed by Security Operations Center (SOC) analysts.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Splunk Enterprise 10.4.0 |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint | CLIENT1 |
| Windows User | sbish |
| Log Source | Windows Security Logs |
| Sysmon | Installed |
| Universal Forwarder | Configured |

---

# Objectives

- Verify Windows Security log collection in Splunk.
- Analyze successful and failed authentication events.
- Understand the difference between user accounts and computer accounts.
- Monitor authentication activity across the endpoint.
- Detect repeated failed authentication attempts.
- Build a basic brute-force detection workflow.

---

# Authentication Events

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4634 | Logoff |
| 4648 | Logon Using Explicit Credentials |

---

# Authentication Analysis

Windows authentication events provide valuable insight into user activity across enterprise endpoints.

During this exercise, successful logons, failed logons, user accounts, and authentication patterns were analyzed to understand normal authentication behavior before creating detection logic.

---

# Computer Accounts vs User Accounts

Windows automatically creates a computer account for every domain-joined system.

Example:

```
CLIENT1$
```

Accounts ending with the **$** symbol represent computer accounts rather than interactive users.

Human users appear using their actual account names.

Example:

```
sbish
```

Understanding this distinction is important during authentication investigations to avoid misinterpreting normal system activity.

---

# Detection Summary

A basic brute-force detection was created by monitoring repeated failed authentication events generated within Windows Security logs.

The detection focuses on identifying accounts receiving multiple failed login attempts, allowing analysts to quickly identify suspicious authentication activity for further investigation.

---

# Investigation Performed

The following information was reviewed during analysis:

- Successful authentication events
- Failed authentication events
- User accounts
- Source hosts
- Authentication timeline
- Repeated failed login attempts

---

# Skills Demonstrated

- Windows Authentication Monitoring
- Windows Security Event Analysis
- Splunk Enterprise
- Authentication Investigation
- Basic Detection Engineering
- SOC Investigation Workflow
- Brute Force Detection Fundamentals

---

# Challenges Encountered

Initially, Windows computer accounts appeared in authentication events instead of the expected user account.

Further investigation confirmed that accounts ending with the **$** symbol represent machine accounts created automatically by Active Directory.

This understanding helped distinguish legitimate system activity from user authentication events during log analysis.

---

# Outcome

Windows authentication logs were successfully collected and analyzed within Splunk Enterprise.

The lab demonstrated the ability to:

- Monitor authentication activity
- Differentiate between computer accounts and user accounts
- Identify repeated failed login attempts
- Perform authentication investigations using Windows Security logs

This use case establishes a strong foundation for future detection engineering and authentication-based threat investigations.

---

# Key Takeaways

- Windows Event ID 4624 represents successful authentication.
- Windows Event ID 4625 represents failed authentication.
- Computer accounts end with the **$** symbol.
- Authentication monitoring is a core responsibility of SOC analysts.
- Understanding normal authentication behavior is essential before building reliable detections.
