# Windows Logon Investigation Queries

## 1. Successful Logons

```spl
index=* EventCode=4624
| table _time host Account_Name Logon_Type Workstation_Name
```

Purpose:

Review successful Windows logon events.

---

## 2. Failed Logons

```spl
index=* EventCode=4625
| table _time host Account_Name Failure_Reason
```

Purpose:

Identify failed authentication attempts.

---

## 3. Logon Type Analysis

```spl
index=* EventCode=4624
| stats count by Logon_Type
| sort -count
```

Purpose:

Identify the most common Windows logon types.

---

## 4. User Authentication Summary

```spl
index=* (EventCode=4624 OR EventCode=4625)
| stats count by Account_Name EventCode
```

Purpose:

Compare successful and failed authentication events by user account.
