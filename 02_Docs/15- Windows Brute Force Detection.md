# Day 15 - Windows Brute Force Detection

## Overview

This lab demonstrates the detection and investigation of repeated Windows authentication failures using Splunk Enterprise.

A controlled brute-force authentication scenario was performed against a Windows domain account to generate Windows Security events. The generated logs were collected in Splunk and analyzed to understand authentication behavior, validate log ingestion, and build a basic detection workflow from a SOC analyst's perspective.

---

# Objective

The objective of this exercise was to:

- Generate Windows authentication events in a controlled environment.
- Validate successful log collection in Splunk Enterprise.
- Analyze failed and successful authentication events.
- Develop a basic brute-force detection query.
- Document the investigation process using enterprise SOC methodology.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM | Splunk Enterprise 10.4.0 |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint | CLIENT1 |
| Test Account | sbish |
| Log Source | Windows Security Logs |
| Sysmon | Enabled |

---

# Attack Scenario

A controlled authentication test was performed by entering an incorrect password multiple times for the **sbish** account, followed by a successful authentication using the correct password.

This generated Windows Security events representing failed and successful logon attempts.

---

# Windows Security Events

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

---

# Activities Performed

- Verified Windows Security log collection.
- Confirmed event ingestion in Splunk Enterprise.
- Generated multiple failed authentication attempts.
- Generated a successful authentication event.
- Investigated Event ID 4625.
- Investigated Event ID 4624.
- Reviewed authentication sequence.
- Created a basic brute-force detection query.
- Documented investigation findings.

---

# Investigation Summary

The investigation identified multiple failed authentication events associated with the **sbish** account.

These failed logon events were immediately followed by a successful authentication event after the correct credentials were provided.

The event sequence matched the expected behavior of the controlled authentication test performed within the lab environment.

---

# Detection Summary

Detection focused on identifying repeated failed authentication attempts recorded in Windows Security logs.

Splunk Enterprise was used to aggregate failed logon events and highlight accounts receiving multiple authentication failures within the observed period.

---

# Skills Demonstrated

- Windows Authentication Monitoring
- Windows Security Event Analysis
- Event ID 4624 Analysis
- Event ID 4625 Analysis
- Splunk Search Processing Language (SPL)
- Security Log Investigation
- Authentication Event Correlation
- Detection Engineering Fundamentals
- SOC Investigation Workflow

---

# Outcome

The simulated brute-force authentication activity was successfully detected and investigated using Splunk Enterprise.

Windows Security logs provided sufficient visibility to reconstruct the authentication sequence and validate the effectiveness of the detection query.

---

# Key Takeaways

- Windows Event ID 4625 provides visibility into failed authentication attempts.
- Windows Event ID 4624 confirms successful authentication events.
- Correlating authentication events helps reconstruct login activity.
- Splunk Enterprise can effectively identify repeated authentication failures using Windows Security logs.
- Authentication monitoring is a fundamental detection use case within enterprise Security Operations Centers.
