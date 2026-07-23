# Day 10 – Splunk Enterprise Deployment

## Overview

This phase focused on deploying **Splunk Enterprise** as the central Security Information and Event Management (SIEM) platform within the Enterprise SOC Home Lab.

Splunk was installed on the Ubuntu Server to provide centralized log collection, security event monitoring, detection engineering, and incident investigation capabilities for Windows-based endpoints deployed in the lab.

---

# Objective

Deploy and configure Splunk Enterprise to establish a centralized logging platform that will be used throughout the SOC lab for:

- Windows event log collection
- Security monitoring
- Detection engineering
- Threat investigation
- Dashboard visualization
- Incident response

---

# Environment

| Component | Details |
|----------|---------|
| SIEM Platform | Splunk Enterprise |
| Version | 10.4.0 |
| Operating System | Ubuntu Server |
| Installation Path | /opt/splunk |
| Web Interface | Port 8000 |
| Role | Centralized SIEM Server |

---

# Implementation

The following tasks were completed during the deployment:

### Splunk Installation

- Downloaded the Splunk Enterprise package.
- Installed Splunk on the Ubuntu Server.
- Extracted the application under `/opt/splunk`.
- Verified a successful installation.

---

### Initial Configuration

- Accepted the Splunk license agreement.
- Configured the administrator account.
- Completed the initial startup configuration.
- Started the Splunk service.

---

### Service Configuration

- Verified Splunk service status.
- Configured Splunk to start automatically during system boot.

---

### Web Interface Validation

- Accessed the Splunk Web interface from the host machine.
- Verified successful connectivity to the SIEM server.
- Confirmed administrator login and dashboard accessibility.

---

# Commands Used

### Extract Package

```bash
sudo tar -xzvf splunk-*.tgz -C /opt
```

### Start Splunk

```bash
sudo ./splunk start --accept-license
```

### Verify Service Status

```bash
sudo ./splunk status
```

### Verify Installed Version

```bash
./splunk version
```

### Enable Boot Start

```bash
sudo ./splunk enable boot-start
```

---

# Skills Demonstrated

- Splunk Enterprise deployment
- Linux server administration
- SIEM configuration
- Service management
- Centralized security monitoring
- Enterprise log management

---

# Outcome

Splunk Enterprise was successfully deployed and configured as the primary SIEM platform for the Enterprise SOC Home Lab.

The environment is now prepared to receive security telemetry from Windows systems, enabling log analysis, detection engineering, alert development, dashboard creation, and incident investigation in the subsequent phases of the project.
