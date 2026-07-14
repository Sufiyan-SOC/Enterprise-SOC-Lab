# Windows Authentication Hunting Queries

## 1. Successful and Failed Logons

```spl
index=* (EventCode=4624 OR EventCode=4625)
| table _time host Account_Name EventCode Logon_Type
```

Purpose:

View successful (4624) and failed (4625) authentication events.

---

## 2. Authentication Timeline

```spl
index=* (EventCode=4624 OR EventCode=4625)
| timechart span=15m count by EventCode
```

Purpose:

Visualize authentication activity over time.

---

## 3. Successful Logons

```spl
index=* EventCode=4624
| table _time host Account_Name Logon_Type
```

Purpose:

Review successful user logons.

---

## 4. Failed Logons

```spl
index=* EventCode=4625
| table _time host Account_Name Failure_Reason
```

Purpose:

Investigate failed authentication attempts.
