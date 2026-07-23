# Day 29 — SMB Brute Force Detection & Authentication Monitoring

## Objective

The objective of this lab was to simulate an SMB password spraying / brute-force attack against a domain-joined Windows endpoint and validate the complete SOC detection workflow using Splunk Enterprise.

This exercise focused on detecting failed authentication attempts, validating Windows Security Events, creating Splunk detections, building monitoring dashboards, and performing security investigations.

---

# Lab Scenario

An attacker machine (Kali Linux) attempted multiple SMB authentications against a Windows 11 Enterprise workstation joined to the Active Directory domain.

The generated Windows Security Events were forwarded to Splunk Enterprise for analysis and detection.

---

# Attack Simulation

**Attack Machine**

- Kali Linux

**Target**

- Windows 11 Enterprise (CLIENT1)

**Technique**

- SMB Password Spraying
- Multiple Failed Logon Attempts
- Successful Authentication Validation

---

# Data Sources

- Windows Security Log
- Event ID 4625 (Failed Logon)
- Event ID 4624 (Successful Logon)

---

# Detection Engineering

The authentication events were analyzed using Splunk Search Processing Language (SPL).

Detection logic was created to identify:

- Multiple failed authentication attempts
- Targeted user accounts
- Source IP addresses
- Authentication timeline

---

# Splunk Components

The following Splunk objects were created during this exercise:

## SPL Queries

- Brute Force Detection
- Failed Authentication Statistics
- Authentication Timeline

## Alert

**Name**

Brute Force Attack Detected

**Purpose**

Detect repeated failed authentication attempts against Windows endpoints.

## Dashboard

Authentication Monitoring

Dashboard panels include:

- Failed Login Trend
- Successful Login Trend
- Top Target Accounts
- Top Source IP Addresses
- Recent Failed Authentication Events
- Authentication Timeline

---

# Investigation Summary

The investigation confirmed:

- Multiple failed authentication attempts
- Source IP identification
- Target account identification
- Successful authentication after repeated failures
- Complete authentication timeline

---

# MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| Brute Force | T1110 |

---

# Skills Demonstrated

- Windows Authentication Monitoring
- Windows Event Log Analysis
- Splunk SPL Development
- Detection Engineering
- Dashboard Development
- Security Monitoring
- Threat Investigation
- MITRE ATT&CK Mapping

---

# Outcome

Successfully detected and investigated an SMB brute-force/password spraying attack against a domain-joined Windows endpoint using Splunk Enterprise.

The lab demonstrates an end-to-end SOC workflow from attack simulation to detection, monitoring, investigation, and security documentation.
