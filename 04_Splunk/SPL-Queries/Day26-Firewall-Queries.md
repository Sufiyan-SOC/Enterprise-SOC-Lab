# Windows Firewall SPL Queries

## Query 1 – Firewall Activity

```spl
index=* Firewall
```

---

## Query 2 – Specific Firewall Rule

```spl
index=* "SOCLab Firewall Rule"
```

---

## Query 3 – Firewall Timeline

```spl
index=* Firewall
| timechart count
```
