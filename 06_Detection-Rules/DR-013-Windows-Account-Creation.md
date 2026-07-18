# Detection Name

Windows User Account Creation

---

## Detection ID

DR-013

---

## Detection Purpose

Detect newly created Windows user accounts that may indicate unauthorized administrative activity or attacker persistence.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

* T1098 – Account Manipulation
* T1078 – Valid Accounts

---

## Data Source

Windows Security Log

Event ID 4720

---

## Detection Logic

Monitor Security Event ID 4720 and investigate every newly created account.

---

## Splunk Detection Query

```spl
index=* source="WinEventLog:Security" EventCode=4720
| table _time ComputerName Account_Name SubjectUserName
```

---

## Severity

High

---

## Normal Output

```text
Time: 11:24

Account_Name:
SOCLabUser

SubjectUserName:
Administrator

ComputerName:
WIN10-LAB
```

### Analysis

* Temporary lab account.
* Created by Administrator.
* Expected administrative activity.

**Status:** ✅ Normal

---

## Suspicious Output

```text
Time: 02:13

Account_Name:
backupadmin

SubjectUserName:
SYSTEM

ComputerName:
FINANCE-PC
```

### Analysis

* Unknown administrator account.
* Created outside business hours.
* Requires immediate investigation.

**Status:** 🚨 High Severity

---

## False Positives

* Helpdesk creating users
* HR onboarding
* Domain administrator tasks

---

## SOC Investigation Checklist

* Verify account owner.
* Review account purpose.
* Check group memberships.
* Correlate with Event ID 4624 (Logon).
* Review related Process Creation events.
* Escalate if unauthorized.

---

## Detection Validation

* ☑ Event Generated
* ☑ Event Received in Splunk
* ☑ Query Returned Results
* ☑ Detection Logic Verified
* ☑ False Positives Reviewed

---

## Detection Confidence

High

Reason:

✔ Tested in Lab

✔ Event Successfully Generated

✔ Event Successfully Ingested

✔ Query Successfully Validated
