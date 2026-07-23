# Day 11 – Windows Log Collection with Splunk Universal Forwarder

## Objective

The objective of this phase was to establish centralized log monitoring by connecting a Windows endpoint to the Splunk SIEM server.

A Splunk Universal Forwarder was deployed on the Windows 11 endpoint to securely collect and forward Windows Event Logs to the Ubuntu-based Splunk Enterprise server for security monitoring and analysis.

---

# Lab Architecture

```
Windows 11 Endpoint
        |
        |
Splunk Universal Forwarder
        |
        |  TCP 9997
        |
Ubuntu Server
(Splunk Enterprise SIEM)
        |
        |
Security Monitoring & Analysis
```

---

# Environment Details

| Component            | Details                    |
| -------------------- | -------------------------- |
| SIEM Platform        | Splunk Enterprise          |
| SIEM Server          | Ubuntu Server              |
| Endpoint             | Windows 11                 |
| Log Forwarding Agent | Splunk Universal Forwarder |
| Communication Port   | TCP 9997                   |
| Project Type         | SOC Analyst Home Lab       |

---

# Tasks Completed

## 1. Configured Splunk Receiving Port

* Enabled Splunk receiving on the server
* Configured TCP port 9997 for incoming log data
* Prepared the Splunk server to receive endpoint telemetry

---

## 2. Installed Splunk Universal Forwarder

* Installed Splunk Universal Forwarder on the Windows 11 endpoint
* Configured connectivity between the Windows endpoint and the Splunk server
* Verified the status of the forwarder service

---

## 3. Configured Windows Event Log Collection

Collected the following Windows logs:

* Security Event Logs
* System Event Logs
* Application Event Logs

These logs are commonly reviewed by SOC analysts for:

* Authentication monitoring
* Failed login detection
* Suspicious activity investigation
* Endpoint troubleshooting

---

## 4. Verified Log Ingestion

Validated successful communication between:

Windows Endpoint → Splunk Forwarder → Splunk SIEM

Confirmed that Windows events were searchable within Splunk.

---

# Commands Used

### Check Splunk Universal Forwarder Status

```cmd
splunk status
```

### Verify Splunk Receiving Port

```bash
sudo ss -tulnp | grep 9997
```

### Search Incoming Events

```spl
index=*
```

---

# Skills Learned

* SIEM log collection architecture
* Splunk Universal Forwarder deployment
* Windows Event Log monitoring
* Endpoint telemetry collection
* Basic Splunk administration
* SOC monitoring workflow

---

# Outcome

Successfully integrated a Windows 11 endpoint with Splunk Enterprise SIEM.

The environment is now capable of collecting and analyzing Windows security telemetry, providing a foundation for future SOC operations such as:

* Threat detection
* Security investigations
* Alert creation
* Incident response workflows

---

#

