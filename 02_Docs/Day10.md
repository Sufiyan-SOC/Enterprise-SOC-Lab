# Day 10 – Splunk Enterprise Installation & SIEM Deployment

## Objective

The objective of this phase was to deploy and configure Splunk Enterprise on an Ubuntu Server to establish a Security Information and Event Management (SIEM) platform for centralized security monitoring.

Splunk was installed as the core monitoring solution that will later collect, analyze, and visualize security events from Windows endpoints and servers.

---

# Lab Architecture

```
                SOC Home Lab Environment

Windows 11 Endpoint
        |
        |
        |  Security Logs
        |
        v

Ubuntu Server
(Splunk Enterprise SIEM)

        |
        |
        v

Log Analysis
Detection
Investigation
Monitoring
```

---

# Environment Details

| Component          | Details              |
| ------------------ | -------------------- |
| SIEM Platform      | Splunk Enterprise    |
| Splunk Version     | 10.4.0               |
| SIEM Server        | Ubuntu Server        |
| Operating System   | Ubuntu Linux         |
| Installation Path  | /opt/splunk          |
| Web Interface Port | 8000                 |
| Project Type       | SOC Analyst Home Lab |

---

# Tasks Completed

## 1. Splunk Enterprise Installation

* Downloaded Splunk Enterprise package
* Transferred Splunk installation file to Ubuntu Server
* Extracted Splunk package into the `/opt` directory
* Verified successful installation

---

## 2. Initial Splunk Configuration

* Accepted Splunk license agreement
* Created Splunk administrator account
* Completed initial setup configuration
* Started Splunk Enterprise service

---

## 3. Splunk Service Management

Configured and verified Splunk service operations:

* Started Splunk daemon
* Checked Splunk service status
* Enabled Splunk boot-start configuration

---

## 4. Splunk Web Interface Setup

* Accessed Splunk Web interface from Windows Host machine
* Verified successful communication between Host and Ubuntu Server
* Logged into Splunk dashboard successfully

---

# Commands Used

### Extract Splunk Package

```bash
sudo tar -xzvf splunk-*.tgz -C /opt
```

### Start Splunk

```bash
sudo ./splunk start --accept-license
```

### Check Splunk Status

```bash
sudo ./splunk status
```

### Verify Splunk Version

```bash
./splunk version
```

### Enable Auto Start

```bash
sudo ./splunk enable boot-start
```

---

# Skills Learned

* SIEM deployment and configuration
* Splunk Enterprise administration
* Linux application management
* Service management in Ubuntu
* Web-based SIEM access
* SOC monitoring environment setup

---

# Outcome

Successfully deployed Splunk Enterprise 10.4.0 on Ubuntu Server.

The SIEM environment is now ready for:

* Windows log collection
* Endpoint monitoring
* Security event analysis
* SPL query investigation
* Alert creation and detection engineering

---

#

