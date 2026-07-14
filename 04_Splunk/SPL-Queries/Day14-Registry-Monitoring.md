# Registry Monitoring Queries

## 1. Verify Sysmon Registry Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
```

Purpose:

Verify that Sysmon Operational logs are successfully ingested into Splunk.

---

## 2. Registry Value Set Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
| table _time Computer User Image TargetObject Details
```

Purpose:

Identify Registry Value Set events recorded by Sysmon.

---

## 3. Registry Activity Summary

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
| stats count by Image
| sort -count
```

Purpose:

Summarize Registry modification activity by process.

---

## 4. Registry Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
| table _time Image TargetObject Details User
```

Purpose:

Investigate Registry modifications by reviewing the modified path, stored value, responsible process, and user.
