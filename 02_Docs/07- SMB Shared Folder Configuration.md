# Day 7 – SMB Shared Folder Configuration

## Overview

Configured an SMB shared folder on the Windows Server Domain Controller and secured access using Share Permissions and NTFS Permissions. The shared folder was successfully accessed from the domain-joined Windows 11 client to verify network file sharing and permission enforcement.

---

## Objectives

- Create an SMB shared folder on the Domain Controller
- Configure Share Permissions
- Configure NTFS Permissions
- Verify network access from a domain-joined client
- Validate file access based on assigned permissions

---

## Implementation Summary

A shared folder named **CompanyData** was created on the Domain Controller and published over SMB. Share Permissions and NTFS Permissions were configured to control access to the shared resource. Connectivity and file access were tested from the Windows 11 Enterprise client after joining it to the Active Directory domain.

---

## Skills Demonstrated

- Windows File Sharing (SMB)
- Share Permissions
- NTFS Permissions
- Windows File Server Administration
- Active Directory Environment
- Windows Client Administration
