# Hardening Checklists

This directory contains high‑impact, practical security hardening checklists for Linux, Windows 11, and Windows Server systems. Each checklist focuses on the **15 most important controls** that significantly reduce attack surface while remaining realistic for enterprise, homelab, and professional environments.

These checklists demonstrate:

- Practical defensive security knowledge  
- Familiarity with CIS Benchmarks and STIG principles  
- Ability to document and communicate security controls  
- Real‑world system administration and hardening skills  

Each checklist includes:

- A description of the control  
- The process to implement it  
- Commands or configuration paths where applicable  

---

## Prerequisites for Using These Checklists

Some hardening steps require tools or system components that may not be installed by default.  
This section lists **required prerequisites** for each platform.

### Linux Prerequisites
The following packages or components should be installed before applying the Linux hardening checklist:

- `auditd` — required for audit logging  
- `aide` — required for file integrity monitoring  
- `ufw` or `firewalld` — required for firewall configuration  
- `google-authenticator` or `libpam-u2f` — required for MFA  
- `clamav` — required for malware scanning  
- `policycoreutils` and `selinux-utils` (SELinux systems)  
- `apparmor` and `apparmor-utils` (AppArmor systems)  

### Windows 11 Prerequisites
Before applying the Windows 11 hardening checklist, ensure:

- Microsoft Defender Antivirus is enabled  
- Microsoft Defender Application Guard (optional) is installed  
- Sysmon is downloaded from Microsoft Sysinternals  
- Group Policy Management Console (GPMC) is installed (Pro/Enterprise)  
- TPM 2.0 is enabled for BitLocker and Credential Guard  
- Windows Security “Core Isolation” features are available  

### Windows Server Prerequisites
Before applying the Windows Server hardening checklist, ensure:

- Sysmon is installed for logging  
- Group Policy Management Console is installed  
- Windows Defender is enabled (Server 2016+)  
- TPM 2.0 is enabled for BitLocker  
- Remote Server Administration Tools (RSAT) installed if managing remotely  
- Windows Event Forwarding infrastructure (optional but recommended)  

---

## Included Checklists

- **linux_checklist.md** — Hardening for common Linux distributions  
- **windows_11_checklist.md** — Hardening for Windows 11 Pro/Enterprise  
- **windows_server_checklist.md** — Hardening for Windows Server 2019/2022  

Use these documents as baselines for securing systems, demonstrating your security skillset, or preparing for interviews.

---

## Copyright (c) 2025 hexwyrm
All rights reserved. This repository is provided solely for the purpose of demonstrating security research and reporting skills to potential employers and recruiters. No permission is granted to copy, modify, distribute, or otherwise use the contents for any other purpose.
