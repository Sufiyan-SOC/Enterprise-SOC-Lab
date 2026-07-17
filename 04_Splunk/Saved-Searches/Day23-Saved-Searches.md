# Saved Search

## Name

Windows Service Installation Monitoring

## Purpose

Monitor newly installed Windows Services.

## SPL

```spl
index=* source="WinEventLog:System" EventCode=7045
| table _time _raw
```

## Schedule

Every 15 Minutes

## Priority

High
