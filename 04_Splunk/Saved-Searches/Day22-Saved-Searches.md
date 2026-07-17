# Saved Search

## Name

Process Access Monitoring

## Purpose

Monitor process-to-process access events on Windows endpoints.

## SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=10
| table _time SourceImage TargetImage GrantedAccess User
```

## Schedule

Every 15 Minutes

## Priority

High
