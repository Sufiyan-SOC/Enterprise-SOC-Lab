# Windows Account Management Queries

## Query 1 – User Account Creation

```spl
index=* source="WinEventLog:Security" EventCode=4720
| table _time ComputerName Account_Name SubjectUserName
```

---

## Query 2 – User Creation Timeline

```spl
index=* source="WinEventLog:Security" EventCode=4720
| timechart count
```

---

## Query 3 – User Creation Count

```spl
index=* source="WinEventLog:Security" EventCode=4720
| stats count by SubjectUserName
| sort -count
```
