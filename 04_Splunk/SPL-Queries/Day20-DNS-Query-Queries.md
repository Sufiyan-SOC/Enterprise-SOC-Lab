# DNS Query SPL Queries

## Query 1 – DNS Query Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=22
| table _time Image QueryName QueryResults User
```

---

## Query 2 – Top Queried Domains

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=22
| stats count by QueryName
| sort -count
```

---

## Query 3 – DNS Queries by Process

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=22
| stats count by Image
| sort -count
```

---

## Query 4 – DNS Queries by User

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=22
| stats count by User
| sort -count
```
