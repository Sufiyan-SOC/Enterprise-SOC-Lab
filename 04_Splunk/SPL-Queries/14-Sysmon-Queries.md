# Day 14 - Sysmon Process Investigation Queries

---

## 1. Verify Sysmon Logs

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
```

---

## 2. View Process Creation Events (Event ID 1)

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
```

---

## 3. Investigate Notepad Execution

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" notepad.exe
```

---

## 4. Investigate Command Prompt Execution

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" cmd.exe
```

---

## 5. Investigate PowerShell Execution

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" powershell.exe
```

---

## 6. Process Hunting (CMD & PowerShell)

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
(Image="*cmd.exe" OR Image="*powershell.exe")
| table _time Image ParentImage CommandLine User Computer
```

---

## 7. Process Execution Statistics

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
| stats count by Image
| sort -count
```

---

## 8. Search by Image Path

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" Image="*powershell.exe"
```

---

## 9. Search by Parent Process

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" ParentImage="*explorer.exe"
```

---

## 10. Display Important Process Fields

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
| table _time Image ParentImage CommandLine User ProcessId Computer
```

---

# Queries Used in Day 14

| Query              | Purpose                                |
| ------------------ | -------------------------------------- |
| Verify Sysmon Logs | Confirm Sysmon data is reaching Splunk |
| EventID=1          | View all Process Creation events       |
| notepad.exe        | Investigate Notepad execution          |
| cmd.exe            | Investigate Command Prompt execution   |
| powershell.exe     | Investigate PowerShell execution       |
| Process Hunting    | Hunt for CMD and PowerShell activity   |
| Process Statistics | Find the most executed processes       |
| Image Search       | Search by executable path              |
| ParentImage Search | Identify parent-child relationships    |
| Table View         | Display important investigation fields |
