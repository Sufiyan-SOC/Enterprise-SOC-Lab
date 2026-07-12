# Saved Searches

## Successful Login Search

```spl
index=* source="WinEventLog:Security" EventCode=4624
```

---

## Failed Login Search

```spl
index=* source="WinEventLog:Security" EventCode=4625
```

---

## Brute Force Detection

```spl
index=* source="WinEventLog:Security" EventCode=4625
| stats count by Account_Name
| where count>=5
```
