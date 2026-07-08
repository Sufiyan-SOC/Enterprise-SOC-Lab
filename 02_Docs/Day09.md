# Day 09 - Ubuntu Server Network Configuration & SSH Setup

## Objective

The objective of Day 09 was to prepare the Ubuntu Server as the future SIEM server by configuring networking, enabling remote access through SSH, and creating a proper project structure for the SOC Lab.

---

## Lab Environment

| Component        | Details                   |
| ---------------- | ------------------------- |
| Hypervisor       | Oracle VirtualBox 7.2.8   |
| Operating System | Ubuntu Server 22.04.5 LTS |
| Hostname         | ubuntu-siem               |
| Username         | socadmin                  |
| RAM              | 3 GB                      |
| CPU              | 2 Cores                   |
| Disk             | 60 GB                     |

---

## Network Configuration

### Adapter 1

* Mode: NAT
* Purpose: Internet access

### Adapter 2

* Mode: Host-Only Adapter
* Purpose: Internal communication with Windows Server and Windows Desktop

### Static IP Configuration

| Device          | IP Address      |
| --------------- | --------------- |
| Windows Server  | 172.16.0.1/24   |
| Windows Desktop | 172.16.0.100/24 |
| Ubuntu SIEM     | 172.16.0.20/24  |

---

## Tasks Completed

* Installed Ubuntu Server 22.04.5 LTS
* Configured Host-Only networking
* Assigned static IP address
* Verified network connectivity
* Configured Netplan
* Applied network configuration
* Fixed interface issues
* Verified connectivity using ping
* Installed and enabled OpenSSH Server
* Tested SSH connectivity
* Created SOC Lab project directory structure

---

## Directory Structure

```text
/home/socadmin/SOC-Lab
├── Downloads
├── Logs
├── Scripts
└── Tools
```

---

## Commands Used

### Check Network Interfaces

```bash
ip addr
```

### Apply Netplan

```bash
sudo netplan apply
```

### Verify IP Address

```bash
ip a
```

### Test Network

```bash
ping 172.16.0.1
ping 172.16.0.100
```

### Check SSH Service

```bash
sudo systemctl status ssh
```

### Test SSH

```bash
ssh socadmin@172.16.0.20
```

### Create Project Structure

```bash
mkdir -p ~/SOC-Lab/{Downloads,Tools,Scripts,Logs}
tree ~/SOC-Lab
```

---

## Skills Learned

* Ubuntu Server administration
* Static IP configuration
* Netplan configuration
* VirtualBox Host-Only networking
* SSH server configuration
* Linux directory management
* Basic network troubleshooting

---

## Challenges Faced

* Host-Only adapter was initially in DOWN state.
* Netplan configuration was overwritten during troubleshooting.
* SSH connection timed out because the Host-Only network was not configured correctly.
* Static IP configuration was verified and made persistent after reboot.

---

## Outcome

Ubuntu Server was successfully prepared as the future SIEM server.

The server now has:

* Stable static IP address
* Working SSH access
* Internet connectivity
* Persistent network configuration after reboot
* Organized SOC Lab workspace

This server is now ready for Splunk Enterprise installation.

