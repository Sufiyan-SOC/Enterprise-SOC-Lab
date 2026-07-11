# Day 13 – Windows Authentication Monitoring (SPL Queries)

## 1. Verify All Events

```spl
index=*
```

---

## 2. View Successful Login Events (Event ID 4624)

```spl
index=* EventCode=4624
```

---

## 3. View Failed Login Events (Event ID 4625)

```spl
index=* EventCode=4625
```

---

## 4. Search Successful Logins for Human Users

```spl
index=* EventCode=4624 Account_Name!="*$"
```

---

## 5. Search Login Events for User "sbish"

```spl
index=* EventCode=4624 sbish
```

---

## 6. Authentication Timeline

```spl
index=* EventCode IN (4624,4625)
| timechart span=1h count by EventCode
```

---

## 7. Top Logged-in Users

```spl
index=* EventCode=4624
| stats count by Account_Name
| sort -count
```

---

## 8. Top Source Hosts

```spl
index=* EventCode=4624
| stats count by host
| sort -count
```

---

## 9. Basic Brute Force Detection

```spl
index=* EventCode=4625
| stats count by Account_Name
| where count>=3
```

---

## 10. View Login Details

```spl
index=* EventCode=4624
| table _time host Account_Name Logon_Type EventCode
```

---

## 11. Count Successful Logins

```spl
index=* EventCode=4624
| stats count
```

---

## 12. Count Failed Logins

```spl
index=* EventCode=4625
| stats count
```

---

## 13. Authentication Events by Host

```spl
index=* EventCode=4624
| stats count by host
```

---

## 14. Authentication Events by User

```spl
index=* EventCode=4624
| stats count by Account_Name
```

---

# Skills Practiced

* Authentication Monitoring
* Successful Login Analysis
* Failed Login Analysis
* Authentication Timeline
* User Activity Monitoring
* Host Activity Monitoring
* Basic Brute Force Detection
* Windows Security Log Investigation
