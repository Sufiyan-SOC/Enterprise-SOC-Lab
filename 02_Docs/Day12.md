# Day 12 – Sysmon Deployment & Advanced Endpoint Telemetry

## Objective

The objective of this phase was to enhance endpoint visibility by deploying Sysmon on the Windows 11 endpoint and integrating its telemetry with Splunk Enterprise.

Sysmon provides detailed security events that help SOC analysts detect suspicious process execution, network activity, file creation, registry modifications, and other endpoint behaviors that are not fully available in standard Windows Event Logs.

---

# Lab Architecture

```
                SOC Home Lab Environment

Windows 11 Endpoint
        │
        │
   Microsoft Sysmon
        │
        │
Windows Event Logs
(Sysmon Operational Log)
        │
        │
Splunk Universal Forwarder
        │
        │ TCP 9997
        │
Ubuntu Server
(Splunk Enterprise SIEM)
        │
        │
Security Monitoring
Detection
Investigation
```

---

# Environment Details

| Component          | Details                    |
| ------------------ | -------------------------- |
| Endpoint           | Windows 11                 |
| Monitoring Tool    | Microsoft Sysmon           |
| SIEM Platform      | Splunk Enterprise 10.4.0   |
| SIEM Server        | Ubuntu Server              |
| Log Collection     | Splunk Universal Forwarder |
| Communication Port | TCP 9997                   |
| Project Type       | SOC Analyst Home Lab       |

---

# Tasks Completed

## 1. Installed Microsoft Sysmon

* Downloaded Microsoft Sysmon
* Accepted the Sysmon license agreement
* Installed Sysmon as a Windows service
* Verified successful installation

---

## 2. Applied Sysmon Configuration

* Applied a production-style Sysmon configuration
* Enabled advanced endpoint monitoring
* Configured event filtering for security visibility

---

## 3. Verified Sysmon Events

Verified that Sysmon was generating events in:

```
Applications and Services Logs
    └── Microsoft
        └── Windows
            └── Sysmon
                └── Operational
```

Confirmed successful event generation.

---

## 4. Integrated Sysmon with Splunk

* Configured Splunk Universal Forwarder to collect Sysmon Operational logs
* Forwarded Sysmon events to Splunk Enterprise
* Verified successful log ingestion

---

## 5. Validated Endpoint Telemetry

Confirmed that Splunk successfully received advanced endpoint events including:

* Process Creation
* Network Connections
* File Creation
* Registry Activity
* Image Loading Events

---

# Commands Used

### Install Sysmon

```cmd
sysmon64.exe -accepteula -i sysmonconfig.xml
```

### Verify Configuration

```cmd
sysmon64.exe -c
```

### Restart Universal Forwarder

```cmd
splunk restart
```

### Verify Sysmon Events in Splunk

```spl
source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
```

### Display Event Counts

```spl
source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
| stats count by EventCode
```

---

# Skills Learned

* Microsoft Sysmon deployment
* Advanced endpoint telemetry
* Endpoint monitoring
* Splunk log ingestion
* Windows security event analysis
* SOC visibility enhancement

---

# Outcome

Successfully deployed Microsoft Sysmon on the Windows 11 endpoint and integrated its telemetry with Splunk Enterprise.

The SOC environment now provides detailed endpoint visibility, enabling more effective threat detection, security investigations, and incident response activities.
