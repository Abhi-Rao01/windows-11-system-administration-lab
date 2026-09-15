# Windows 11 System Administration Lab

## 📌 Project Overview

This project documents a hands-on Windows 11 system administration lab performed in a virtual environment. The lab focuses on common administrative, troubleshooting, and validation tasks used in IT Support and System Administration roles.

The project includes computer configuration, local user and group management, NTFS permissions, Windows Update verification, Windows Security checks, firewall configuration, service management, performance monitoring, Event Viewer analysis, disk management, and network verification.

---

## 🎯 Project Objectives

- Rename and verify the Windows client computer.
- Create and manage local user accounts.
- Assign local administrative privileges.
- Verify users with Command Prompt and PowerShell.
- Configure NTFS permissions for shared folders.
- Test read-only and modify access.
- Check Windows Update and update history.
- Review hardware detection in Device Manager.
- Validate Windows Security and Defender status.
- Inspect firewall profiles and create firewall rules.
- Manage services through GUI and PowerShell.
- Monitor system performance using Task Manager.
- Review Event Viewer logs and create a test event.
- Add, initialize, and configure a second disk.
- Verify disks and volumes with PowerShell.
- Verify TCP/IP configuration using `ipconfig /all`.

---

## 🛠️ Lab Environment

| Component | Details |
|---|---|
| Operating System | Windows 11 Pro |
| Virtualization Platform | VMware Workstation |
| System Type | x64-based virtual machine |
| Administration Tools | Computer Management, lusrmgr.msc, PowerShell, CMD |
| Security Tools | Windows Security, Microsoft Defender, Windows Firewall |
| Monitoring Tools | Task Manager, Event Viewer |
| Storage Tools | Disk Management, PowerShell |
| Network Tools | ipconfig /all |

---

# Part 1 — Computer Configuration

## Step 1: Check Current Computer Name

I first reviewed the current computer name before making any configuration changes.

![Current Computer Name](images/01-computer-name-before.png)

## Step 2: Rename the Computer

I renamed the Windows 11 client computer to use a clearer administrative naming format.

![Rename Computer](images/02-rename-computer.png)

## Step 3: Verify the New Computer Name

After renaming, I confirmed that the updated computer name was applied successfully.

![Computer Name Verified](images/03-computer-name-verified.png)

---

# Part 2 — Local Users and Groups Management

## Step 4: Open Local Users and Groups

I opened the Local Users and Groups console to manage local accounts.

![Open lusrmgr](images/04-local-user-console.png)

## Step 5: Create the Helpdesk User

I created a local standard support account named **helpdesk-user**.

![Create Helpdesk User](images/04-creat-helpdesk-user.png)

![Helpdesk User Created](images/05-helpdesk-user-created.png)

## Step 6: Review Local User Console

I reviewed the Users console to verify the new account.

![Local User Console](images/05-local-user-console.png)

## Step 7: Create the IT Admin User

I created another local account named **it-admin** for administrative tasks.

![Create IT Admin User](images/06-create-it-admin.png)

## Step 8: Verify Created Users

I confirmed that both local users were created successfully.

![Local Users Created](images/07-local-users-created.png)

## Step 9: Review Administrators Group

I checked the local **Administrators** group before adding the new admin user.

![Administrators Group Before](images/08-administrators-befor.png)

## Step 10: Add IT Admin to Administrators Group

I added **it-admin** to the local Administrators group.

![Add IT Admin](images/09-add-it-admin.png)

![IT Admin Added](images/10-it-admin-added.png)

## Step 11: Verify Users with Command Prompt

I used the `net users` command to list local accounts.

![net users](images/11-net-users.png)

## Step 12: Review Helpdesk User Details

I checked the account configuration for the helpdesk user.

![Helpdesk User Details](images/12-helpdesk-user-details.png)

## Step 13: Verify Accounts with PowerShell

I used `Get-LocalUser` to verify local user information.

![Get-LocalUser](images/13-get-localuser.png)

## Step 14: Verify Administrator Membership in PowerShell

I validated administrative group membership using PowerShell.

![Admin Group PowerShell](images/14-admin-group-powershell.png)

---

# Part 3 — NTFS Permissions Lab

## Step 15: Create the Shared Data Folder

I created a shared working folder to test NTFS access control.

![Shared Data Folder](images/17-shared-data-folder.png)

## Step 16: Review Original Permissions

I reviewed the default permissions on the folder before making changes.

![Original Permissions](images/18-original-permissions.png)

## Step 17: Add Helpdesk User with Read-Only Access

I assigned the helpdesk account limited read-only access.

![Add Helpdesk Read Only](images/19-add-helpdesk-read-only.png)

![Helpdesk Read Only](images/20-helpdesk-read-only.png)

## Step 18: Test Helpdesk Login

I signed in as the helpdesk user to test access.

![Helpdesk Login](images/21-helpdesk-login.png)

## Step 19: Review NTFS Permissions Before Fix

I reviewed the permissions again to troubleshoot or refine access.

![NTFS Permissions Before Fix](images/21-ntfs-permissions-before-fix.png)

## Step 20: Configure Custom NTFS Permissions

I adjusted permissions using custom NTFS settings.

![NTFS Custom Permissions](images/22-ntfs-custom-permissions.png)

## Step 21: Validate Restricted Save Access

I confirmed that the helpdesk user was restricted from saving where modify access was not allowed.

![Helpdesk Save Restricted](images/23-helpdesk-save-restricted.png)

## Step 22: Validate IT Admin Modify Access

I verified that the IT admin account was able to modify files successfully.

![IT Admin Modify Success](images/24-it-admin-modify-success.png)

## Step 23: Re-test Helpdesk Access

I performed an overwrite or write test again with the helpdesk user.

![Helpdesk Overwrite Test](images/25-helpdesk-overwrite-test.png)

## Step 24: Sign in as IT Admin

I logged in again with the administrative account for final verification.

![IT Admin Login](images/26-it-admin-login.png)

## Step 25: Final NTFS Permission Verification

I confirmed the final access configuration.

![Final NTFS Permissions](images/27-final-ntfs-permissions.png)

---

# Part 4 — Windows Update

## Step 26: Check Windows Update Status

I checked for updates and confirmed update completion.

![Windows Update Check Complete](images/28-windows-upate-check-complete.png)

## Step 27: Review Quality Update History

I reviewed recently installed quality updates.

![Quality Update History](images/29-quality-update-history.png)

## Step 28: Review Driver Update History

I reviewed installed driver updates.

![Driver Update History](images/30-driver-update-history.png)

---

# Part 5 — Device Manager and Windows Security

## Step 29: Open Device Manager

I opened Device Manager to inspect installed hardware.

![Open Device Manager](images/31-open-device-manager.png)

## Step 30: Review Device Manager Overview

I verified that virtual hardware was detected correctly.

![Device Manager Overview](images/32-device-manager-overview.png)

## Step 31: Review Windows Security Dashboard

I checked the overall Windows Security status.

![Windows Security Dashboard](images/33-windows-security-dashbord.png)

## Step 32: Run Defender Quick Scan

I reviewed the results of a quick malware scan.

![Defender Quick Scan Result](images/34-defender-quick-scan-result.png)

## Step 33: Verify Defender Status in PowerShell

I validated Windows Defender information using PowerShell.

![Defender PowerShell Status](images/35-defender-powershell-status.png)

---

# Part 6 — Windows Firewall Management

## Step 34: Review Firewall Network Profiles

I opened Windows Firewall settings and reviewed the active network protection profiles.

![Firewall Network Profiles](images/36-firewall-network-profiles.png)

## Step 35: Verify Firewall Profiles in PowerShell

I used PowerShell to validate firewall profile status.

![Firewall Profiles PowerShell](images/37-firewall-profiles-powershell.png)

## Step 36: Create a Firewall Rule

I created a test or administrative firewall rule.

![Create Firewall Rule](images/38-create-firewall-rule.png)

## Step 37: Verify the Firewall Rule

I checked that the rule was created successfully.

![Firewall Rule Verification](images/39-firewall-rule-verification.png)

## Step 38: Review Firewall Rule in GUI

I confirmed the rule in the graphical firewall console.

![Firewall Rule GUI](images/40-firewall-rule-gui.png)

---

# Part 7 — Services Management

## Step 39: Open the Services Console

I opened the Windows Services management console.

![Service Console](images/41-service-console.png)

## Step 40: Review Windows Search Service Properties

I examined the properties of the Windows Search service.

![Windows Search Properties](images/42-windows-serch-properties.png)

## Step 41: Stop the Windows Search Service

I stopped the service to validate service management behavior.

![Windows Search Stopped](images/43-windows-serch-stopped.png)

## Step 42: Verify Service State in PowerShell

I used PowerShell to confirm the service state.

![Windows Search PowerShell](images/44-windows-search-powershell.png)

---

# Part 8 — Performance Monitoring with Task Manager

## Step 43: Review Running Processes

I inspected running processes in Task Manager.

![Task Manager Processes](images/45-task-manager-processes.png)

## Step 44: Review CPU Usage

I monitored CPU utilization.

![Task Manager CPU](images/46-task-manager-cpu.png)

## Step 45: Review Memory Usage

I monitored memory usage.

![Task Manager Memory](images/47-task-manager-memory.png)

## Step 46: Review Network Usage

I monitored network usage in Task Manager.

![Task Manager Network](images/48-task-manager-network.png)

---

# Part 9 — Event Viewer

## Step 47: Open Event Viewer

I opened Event Viewer to inspect Windows logs.

![Event Viewer Overview](images/50-event-viewer-overview.png)

## Step 48: Review System Event Logs

I reviewed system log entries.

![System Event Logs](images/51-system-event-logs.png)

## Step 49: Review Event Details

I opened an event entry to inspect detailed information.

![System Event Details](images/52-system-event-details.png)

## Step 50: Review Errors and Warnings

I reviewed warning and error entries for troubleshooting practice.

![System Errors and Warnings](images/53-system-errors-warnings.png)

## Step 51: Create a Test Event

I generated a custom or test event.

![Create Test Event](images/54-create-test-event.png)

## Step 52: Verify the Custom Event

I checked that the test event appeared correctly.

![Custom Event Verification](images/55-custom-event-verification.png)

## Step 53: Verify Event Log in PowerShell

I used PowerShell to confirm event log data.

![Custom Event PowerShell](images/56-custom-event-powershell.png)

---

# Part 10 — Disk Management

## Step 54: Add a Second Virtual Disk

I added a second disk to the virtual machine through VMware settings.

![VMware Second Disk Added](images/57-vmware-second-disk-added.png)

## Step 55: Detect New Disk

I verified that the new disk appeared as uninitialized.

![New Disk Not Initialized](images/58-new-disk-not-initialized.png)

## Step 56: Initialize Disk as GPT

I initialized the disk using GPT partition style.

![Disk Initialized GPT](images/59-disk-initialized-gpt.png)

## Step 57: Complete Disk Configuration

I created and configured the new volume in Disk Management.

![Disk Management Final](images/60-disk-management-final.png)

## Step 58: Verify New Drive in File Explorer

I confirmed that the new drive was available in File Explorer.

![New Drive File Explorer](images/61-new-drive-file-explorer.png)

## Step 59: Verify Disks with PowerShell

I used `Get-Disk` to validate the disk configuration.

![Get-Disk PowerShell](images/62-get-disk-powershell.png)

## Step 60: Verify Volumes with PowerShell

I used `Get-Volume` to verify the volume configuration.

![Get-Volume PowerShell](images/63-get-volume-powershell.png)

---

# Part 11 — Network Verification

## Step 61: Verify TCP/IP Configuration

I used:

```cmd
ipconfig /all
```

to review the full network configuration.

![ipconfig all](images/64-ipconfig-all.png)

This helped verify:

- IPv4 addressing
- DHCP status
- DNS server configuration
- Adapter details
- Gateway information

---

# 🔧 Skills Demonstrated

- Windows 11 Administration
- Local Users and Groups
- Group Membership Management
- NTFS Permissions
- Access Control Testing
- Windows Update Management
- Device Manager
- Windows Security / Microsoft Defender
- Windows Firewall
- Service Management
- Task Manager Monitoring
- Event Viewer Troubleshooting
- Disk Management
- PowerShell Administration
- Command Prompt
- Network Verification
- Virtual Machine Administration
- Troubleshooting
- Technical Documentation

---

# 📚 What I Learned

This project helped me practice real Windows administrative tasks in a structured virtual lab.

I strengthened my understanding of:

- user and privilege management
- access control and permissions
- Windows update and security validation
- firewall configuration
- service administration
- system monitoring
- event log analysis
- disk provisioning
- PowerShell-based verification
- network troubleshooting

This lab reflects practical skills used in IT Support and System Administration roles.

---

# ✅ Project Conclusion

In this project, I completed a wide range of Windows 11 administration and troubleshooting tasks in a virtual environment.

I created and validated local user accounts, configured permissions, reviewed updates and security settings, managed services and firewall rules, analyzed event logs, added storage, and verified network settings.

This project demonstrates hands-on ability in Windows system administration and provides a strong foundation for future labs involving Windows Server, Active Directory, PowerShell, and enterprise support tasks.

---

## 👤 Author

**Abhishek Kumar**  
Aspiring IT Support / System Administration Professional

`Windows | VMware | PowerShell | Networking | IT Support | System Administration`
