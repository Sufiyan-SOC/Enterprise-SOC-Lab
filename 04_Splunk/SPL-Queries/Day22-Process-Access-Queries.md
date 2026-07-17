# Process Access SPL Queries

## Query 1 – Process Access Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=10
| table _time SourceImage TargetImage GrantedAccess User
```

---

## Query 2 – Source Processes

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=10
| stats count by SourceImage
| sort -count
```

---

## Query 3 – Target Processes

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=10
| stats count by TargetImage
| sort -count
```
