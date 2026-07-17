# Windows Service SPL Queries

## Query 1 – Service Installation Events

```spl
index=* source="WinEventLog:System" EventCode=7045
| table _time _raw
```

---

## Query 2 – Service Installation Timeline

```spl
index=* source="WinEventLog:System" EventCode=7045
| timechart count
```

---

## Query 3 – Service Installation Count

```spl
index=* source="WinEventLog:System" EventCode=7045
| stats count
```
