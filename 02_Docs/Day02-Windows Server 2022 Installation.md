# Day 02 - Windows Server 2022 Installation

## Overview

This phase focuses on deploying the primary Windows Server 2022 virtual machine that will later serve as the Domain Controller (DC01) for the Enterprise SOC Lab environment.

The server acts as the foundation for Active Directory, DNS, DHCP, centralized authentication, and domain-based administration.

---

## Objective

Deploy and configure a Windows Server 2022 virtual machine to prepare the environment for Active Directory Domain Services (AD DS) installation.

---

## Lab Environment

| Component | Configuration |
|-----------|---------------|
| Hypervisor | Oracle VirtualBox |
| Operating System | Windows Server 2022 Standard (Desktop Experience) |
| VM Name | DC01 |
| Memory | 3072 MB RAM |
| Processor | 2 vCPUs |
| Storage | 50 GB Dynamic VDI |
| Network | NAT + Internal Network |

---

## Implementation Steps

1. Created a new virtual machine in Oracle VirtualBox.
2. Attached the Windows Server 2022 ISO image.
3. Installed **Windows Server 2022 Standard (Desktop Experience)**.
4. Configured the local Administrator account.
5. Renamed the server to **DC01**.
6. Restarted the server to apply the hostname changes.
7. Verified successful installation using Server Manager and System Properties.

---

## Result

Windows Server 2022 was successfully deployed and configured.

The server is now prepared for the installation of Active Directory Domain Services (AD DS), DNS, and DHCP in the following phases of the Enterprise SOC Lab.

---

## Validation

The following checks were performed to verify the installation:

- Windows Server booted successfully.
- Server Manager loaded without errors.
- Computer name changed to **DC01**.
- Administrator account configured successfully.
- System restart completed successfully.

---

## Skills Demonstrated

- Windows Server Deployment
- Virtual Machine Provisioning
- Windows Server Administration
- Enterprise Host Preparation
- VirtualBox Configuration

---

## Lessons Learned

- Differences between **Server Core** and **Desktop Experience** installations.
- Importance of assigning appropriate virtual hardware resources.
- Best practice of renaming the server before promoting it to a Domain Controller.
- Preparing an enterprise server for Active Directory deployment.
