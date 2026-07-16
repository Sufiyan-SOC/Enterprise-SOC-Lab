# Saved Search

## Name

File Creation Monitoring

## Purpose

Monitor newly created files on Windows endpoints.

## SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=11
| table _time Image TargetFilename User
```

## Schedule

Every 15 Minutes

## Priority

Medium
