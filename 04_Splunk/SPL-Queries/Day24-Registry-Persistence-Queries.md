# Registry Persistence SPL Queries

## Query 1 – Registry Value Set Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=13
| table _time _raw
```

---

## Query 2 – Registry Modification by Process

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=13
| stats count by Image
| sort -count
```

---

## Query 3 – Registry Activity Timeline

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=13
| timechart count
```
