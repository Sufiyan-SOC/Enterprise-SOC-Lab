# Saved Search

## Name

Windows User Account Creation Monitoring

## Purpose

Detect newly created Windows user accounts.

## SPL

```spl
index=* source="WinEventLog:Security" EventCode=4720
| table _time ComputerName Account_Name SubjectUserName
```

## Schedule

Every 15 Minutes

## Priority

High
