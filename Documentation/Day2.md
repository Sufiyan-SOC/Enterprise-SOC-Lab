Day 2 - Windows Server 2022 Installation

Objective

Install Windows Server 2022 in VirtualBox and prepare it for Active Directory installation.

Environment

- Hypervisor: VirtualBox
- VM Name: DC01
- RAM: 3075 MB
- CPU: 2 Cores
- Disk: 50 GB (Dynamic VDI)

Steps Performed

1. Created a new VirtualBox virtual machine.
2. Attached the Windows Server 2022 ISO.
3. Installed Windows Server 2022 Standard (Desktop Experience).
4. Created the Administrator account.
5. Renamed the computer to DC01.
6. Restarted the server after the rename.

Result

Windows Server 2022 was installed successfully and is ready for Active Directory Domain Services (AD DS) installation.

Screenshots

- Screenshot 1: VirtualBox VM Settings
- Screenshot 2: Windows Server Desktop
- Screenshot 3: Server Manager
- Screenshot 4: System Properties (Computer Name: DC01)

Lessons Learned

- Difference between Windows Server Core and Desktop Experience.
- Importance of assigning proper RAM and CPU.
- Why computer renaming is done before installing Active Directory.
