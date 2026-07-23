# Day 03 – Active Directory Domain Services (AD DS)

## Objective

Install the Active Directory Domain Services (AD DS) role and promote the Windows Server 2022 system to the first Domain Controller of a new Active Directory forest.

---

## Environment

| Component | Value |
|-----------|-------|
| Operating System | Windows Server 2022 |
| Hostname | DC01 |
| Domain | corp.local |
| Network | Internal Network |

---

## Prerequisites

- Windows Server 2022 installed
- Hostname changed to **DC01**
- Static IP address configured
- Administrative privileges available

---

## Configuration Performed

### 1. Network Configuration

Configured a static IP address for the Domain Controller.

| Setting | Value |
|---------|-------|
| IP Address | 172.16.0.1 |
| Subnet Mask | 255.255.255.0 |
| Preferred DNS | 127.0.0.1 |

---

### 2. Active Directory Domain Services Installation

Installed the **Active Directory Domain Services (AD DS)** role using **Server Manager → Add Roles and Features**.

The installation included the required management tools.

---

### 3. Domain Controller Promotion

The server was promoted to a Domain Controller by creating a new Active Directory forest.

| Configuration | Value |
|--------------|-------|
| Forest | New Forest |
| Root Domain | corp.local |
| DNS Server | Installed |
| Global Catalog | Enabled |
| DSRM Password | Configured |

The server restarted automatically after the promotion process completed.

---

## Validation

The following checks were performed after the reboot:

- Active Directory Users and Computers opened successfully.
- Active Directory Domains and Trusts was available.
- DNS Manager displayed the **corp.local** forward lookup zone.
- DC01 was verified as the first Domain Controller of the forest.
- Active Directory services were operating normally.

---


## Result

Windows Server 2022 was successfully promoted to the first Domain Controller for the **corp.local** Active Directory forest. The environment is now prepared for centralized authentication, domain management, and enterprise administration.
