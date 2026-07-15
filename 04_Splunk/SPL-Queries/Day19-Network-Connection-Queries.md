# Network Connection SPL Queries

## Query 1 – Network Connection Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| table _time Image DestinationIp DestinationPort Protocol
```

---

## Query 2 – Processes Creating Network Connections

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| stats count by Image
| sort -count
```

---

## Query 3 – Top Destination IPs

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| stats count by DestinationIp
| sort -count
```

---

## Query 4 – Top Destination Ports

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=3
| stats count by DestinationPort
| sort -count
```
