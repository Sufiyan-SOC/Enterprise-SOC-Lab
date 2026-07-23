# Day 08 - Ubuntu Server Installation & Initial Configuration

## Objective

The objective of Day 08 was to deploy the Ubuntu Server that will act as the SIEM server for the SOC Lab. The server was installed, basic configuration was completed, and the system was prepared for future Splunk Enterprise deployment.

---

# Lab Environment

| Component        | Details                   |
| ---------------- | ------------------------- |
| Hypervisor       | Oracle VirtualBox 7.2.8   |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Hostname         | ubuntu-siem               |
| Username         | socadmin                  |
| RAM              | 3 GB                      |
| CPU              | 2 Cores                   |
| Disk Size        | 60 GB                     |
| Architecture     | x86_64                    |

---

# Objectives Completed

* Created Ubuntu Server Virtual Machine
* Installed Ubuntu Server 22.04.5 LTS
* Configured hostname
* Created administrator user
* Updated system packages
* Verified internet connectivity
* Verified system information
* Verified disk space
* Prepared server for SIEM deployment

---

# Installation Details

## Virtual Machine Configuration

| Setting | Value           |
| ------- | --------------- |
| Name    | Ubuntu-SIEM     |
| OS Type | Ubuntu (64-bit) |
| RAM     | 3 GB            |
| CPU     | 2 vCPU          |
| Disk    | 60 GB (VDI)     |

---

# System Verification

The following commands were used to verify the operating system and hardware configuration.

## Ubuntu Version

```bash
lsb_release -a
```

---

## System Architecture

```bash
uname -m
```

---

## Hostname

```bash
hostnamectl
```

---

## Disk Usage

```bash
df -h
```

---

## Memory Information

```bash
free -h
```

---

## Internet Connectivity

```bash
ping google.com
```

---

# Package Update

The operating system was updated before installing any software.

```bash
sudo apt update
sudo apt upgrade -y
```

---

# Skills Learned

* Ubuntu Server Installation
* Virtual Machine Deployment
* Linux System Verification
* Package Management
* Disk Verification
* Memory Verification
* Basic Linux Administration
* Server Preparation

---

# Challenges Faced

* Selected appropriate virtual hardware resources.
* Verified operating system installation.
* Confirmed internet connectivity before software installation.
* Prepared the server for future SIEM deployment.

---

# Key Takeaways

* Ubuntu Server provides a stable platform for SIEM deployment.
* System verification is essential before installing enterprise applications.
* Keeping the operating system updated reduces compatibility and security issues.
* Proper server preparation simplifies future deployment tasks.

---

