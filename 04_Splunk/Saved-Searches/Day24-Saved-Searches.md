# Saved Search

## Name

Registry Persistence Monitoring

## Purpose

Monitor Windows Registry modifications that may indicate persistence.

## SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=13
| table _time _raw
```

## Schedule

Every 15 Minutes

## Priority

High
