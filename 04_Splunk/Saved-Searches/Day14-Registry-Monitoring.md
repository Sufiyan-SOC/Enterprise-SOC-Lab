# Saved Searches

## Registry Event Detection

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
```

Purpose:

Quickly identify Registry Value Set events.

---

## Registry Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
| table _time Image TargetObject User
```

Purpose:

Review Registry modifications during investigations.
