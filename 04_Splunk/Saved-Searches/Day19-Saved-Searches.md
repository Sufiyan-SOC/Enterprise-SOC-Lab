# Saved Search

## Name

Network Connection Monitoring

## Purpose

Monitor outbound network connections initiated by Windows processes.

## SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| table _time Image DestinationIp DestinationPort Protocol User
```

## Recommended Schedule

Every 15 minutes

## Priority

Medium
