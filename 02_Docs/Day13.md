# Day 13 - Windows Authentication Monitoring & Basic Brute Force Detection

## Objective

The objective of Day 13 was to learn how Windows authentication events are collected and analyzed in Splunk Enterprise. The focus was on identifying successful logins, failed logins, authentication trends, and detecting basic brute-force activity using SPL queries.

---

# Lab Environment

| Component           | Details                   |
| ------------------- | ------------------------- |
| SIEM                | Splunk Enterprise 10.4.0  |
| Operating System    | Ubuntu Server 22.04.5 LTS |
| Windows Endpoint    | CLIENT1                   |
| Windows User        | sbish                     |
| Log Source          | Windows Security Logs     |
| Sysmon              | Installed and Forwarding  |
| Universal Forwarder | Installed and Running     |

---

# Objectives Completed

* Verified Splunk service health
* Verified Windows log ingestion
* Investigated Successful Login Events (4624)
* Investigated Failed Login Events (4625)
* Learned Windows Machine Account vs Human User
* Created Authentication Timeline
* Identified Top Logged-in Users
* Identified Top Source Hosts
* Detected Basic Brute Force Attempts using SPL

---

# Authentication Event IDs

| Event ID | Description                      |
| -------- | -------------------------------- |
| 4624     | Successful Logon                 |
| 4625     | Failed Logon                     |
| 4634     | Logoff                           |
| 4648     | Logon using Explicit Credentials |

---

# Important Concepts Learned

## Machine Account

Windows automatically creates a computer account ending with the `$` symbol.

Example:

```text
CLIENT1$
```

This represents the computer itself and is different from a human user.

---

## Human User

Example:

```text
sbish
```

This represents the actual user logging into Windows.

---

# SPL Queries Used

## 1. Verify All Events

```spl
index=*
```

---

## 2. Successful Login Events

```spl
index=* EventCode=4624
```

---

## 3. Failed Login Events

```spl
index=* EventCode=4625
```

---

## 4. Authentication Timeline

```spl
index=* EventCode IN (4624,4625)
| timechart span=1h count by EventCode
```

---

## 5. Top Logged-in Users

```spl
index=* EventCode=4624
| stats count by Account_Name
| sort -count
```

---

## 6. Top Source Hosts

```spl
index=* EventCode=4624
| stats count by host
| sort -count
```

---

## 7. Basic Brute Force Detection

```spl
index=* EventCode=4625
| stats count by Account_Name
| where count>=3
```

---

# Skills Learned

* Splunk Search Processing Language (SPL)
* Windows Authentication Monitoring
* Windows Security Event Analysis
* Authentication Trend Analysis
* User Activity Monitoring
* Host Activity Monitoring
* Basic Threat Hunting
* Brute Force Detection
* SOC Investigation Workflow

---

# Challenges Faced

* Machine account (`CLIENT1$`) initially appeared instead of the expected human user.
* Learned the difference between computer accounts and user accounts.
* Adjusted SPL queries to correctly analyze authentication events.
* Verified authentication events using the Windows Security log source.

---

# Outcome

Successfully monitored Windows authentication events in Splunk Enterprise.

The SIEM can now:

* Monitor successful user logins
* Detect failed authentication attempts
* Differentiate between machine accounts and human users
* Identify active users and hosts
* Detect simple brute-force activity using SPL queries

This completes the authentication monitoring phase of the SOC Lab and prepares the environment for advanced Sysmon-based threat hunting.

---

# Key Takeaways

* Event ID 4624 indicates a successful logon.
* Event ID 4625 indicates a failed logon.
* Machine accounts end with the `$` symbol.
* SPL can be used to quickly investigate authentication activity.
* Authentication monitoring is one of the first responsibilities of a SOC Analyst.

---

