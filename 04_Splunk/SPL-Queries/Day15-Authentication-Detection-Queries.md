# Authentication Detection Queries

## Successful Login

```spl
index=* source="WinEventLog:Security" EventCode=4624
```

---

## Failed Login

```spl
index=* source="WinEventLog:Security" EventCode=4625
```

---

## Failed Login Count

```spl
index=* source="WinEventLog:Security" EventCode=4625
| stats count by Account_Name
| sort -count
```

---

## Authentication Timeline

```spl
index=* source="WinEventLog:Security" (EventCode=4624 OR EventCode=4625)
| sort _time
| table _time EventCode Account_Name host Logon_Type
```

---

## Top Targeted Users

```spl
index=* source="WinEventLog:Security" EventCode=4625
| stats count by Account_Name
| sort -count
| head 5
```

---

## Basic Brute Force Detection

```spl
index=* source="WinEventLog:Security" EventCode=4625
| stats count by Account_Name
| where count>=5
| sort -count
```
