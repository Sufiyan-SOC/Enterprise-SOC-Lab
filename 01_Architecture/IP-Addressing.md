# IP Addressing Plan

| System | Role | Network | IP Address |
|---------|------|----------|------------|
| DC01 | Domain Controller | NAT | 10.0.2.15 |
| DC01 | Internal | 172.16.0.1 |
| CLIENT1 | Domain Client | Internal | 172.16.0.100 |
| Ubuntu Server | NAT | 10.0.2.15 |
| Ubuntu Server | Internal | 172.16.0.20 |
| Ubuntu Server | Host-Only | 192.168.56.10 |
| Kali Linux | NAT | 10.0.2.15 |
| Kali Linux | Internal | 172.16.0.101 |

---

## Domain Information

Domain

corp.local

---

DNS

Internal

127.0.0.1

External

10.61.60.188
