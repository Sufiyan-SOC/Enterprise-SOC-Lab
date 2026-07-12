# Day 15 - Brute Force Attack Simulation & Detection

## Objective

The objective of Day 15 was to simulate a controlled brute-force authentication scenario in a Windows lab environment and investigate the generated security events using Splunk Enterprise.

The focus was on understanding how failed authentication attempts appear in Windows Security logs, building a detection query, and documenting the investigation process from a SOC analyst's perspective.

---

# Lab Environment

| Component        | Details                   |
| ---------------- | ------------------------- |
| SIEM             | Splunk Enterprise 10.4.0  |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint | CLIENT1                   |
| Test User        | sbish                     |
| Log Source       | Windows Security Logs     |
| Sysmon           | Enabled                   |

---

# Scenario

A controlled authentication test was performed by intentionally entering an incorrect password five times, followed by a successful login using the correct credentials.

This activity generated Windows authentication events that were investigated inside Splunk.

---

# Activities Performed

* Verified SIEM health
* Verified Windows Security log ingestion
* Generated failed authentication attempts
* Verified successful authentication
* Investigated Event ID 4625
* Investigated Event ID 4624
* Built an authentication timeline
* Identified the targeted account
* Created a basic brute-force detection query
* Documented the investigation findings

---

# Windows Security Events Used

| Event ID | Description      |
| -------- | ---------------- |
| 4624     | Successful Logon |
| 4625     | Failed Logon     |

---

# Investigation Summary

The generated authentication events showed multiple failed login attempts against the **sbish** account followed by a successful login.

Authentication analysis confirmed that the events matched the expected behavior of a controlled brute-force simulation within the lab environment.

---

# Detection Logic

The investigation focused on identifying accounts with repeated failed login attempts.

A threshold-based detection approach was used to highlight accounts that exceeded the expected number of authentication failures.

---

# Skills Learned

* Windows Authentication Monitoring
* Event ID 4624 Analysis
* Event ID 4625 Analysis
* Authentication Timeline Analysis
* SPL Aggregation
* Detection Rule Creation
* Basic Threat Detection
* SOC Investigation Workflow

---


# Outcome

Successfully simulated a brute-force authentication scenario and detected the generated activity using Splunk Enterprise.

The investigation demonstrated how Windows Security Events can be used to identify repeated authentication failures and support incident analysis.

---

# Key Takeaways

* Multiple Event ID 4625 events may indicate password guessing or brute-force activity.
* Authentication timelines help analysts understand event sequences.
* Threshold-based detection improves analyst efficiency.
* Windows Security logs provide critical visibility into authentication activity.

---
