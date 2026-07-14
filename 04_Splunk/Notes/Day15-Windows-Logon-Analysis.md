# Windows Logon Analysis

## Overview

Windows authentication logs provide visibility into user access across endpoints. Understanding logon behavior helps analysts identify unauthorized access, credential attacks, and abnormal authentication patterns.

---

## Windows Security Events

4624

Successful Logon

4625

Failed Logon

---

## Important Fields

| Field            | Description                  |
| ---------------- | ---------------------------- |
| Account_Name     | User account                 |
| Logon_Type       | Authentication method        |
| Workstation_Name | Source workstation           |
| Failure_Reason   | Failed authentication reason |
| _time            | Event timestamp              |

---

## Common Logon Types

2 – Interactive

3 – Network

5 – Service

10 – Remote Desktop

---

## Investigation Checklist

* Verify the user account.
* Review authentication result.
* Identify logon type.
* Validate workstation.
* Compare with previous authentication activity.
