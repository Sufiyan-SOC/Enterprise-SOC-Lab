# File Creation SPL Queries

## Query 1 – File Creation Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11
| table _time Image TargetFilename User
```

---

## Query 2 – Top Created Files

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11
| stats count by TargetFilename
| sort -count
```

---

## Query 3 – File Creation by Process

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11
| stats count by Image
| sort -count
```

---

## Query 4 – Monitor SOC-Lab Folder

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11 TargetFilename="*SOC-Lab*"
| table _time Image TargetFilename User
```
