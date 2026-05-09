# Windows Server Hardening Checklist — Top 15 Critical Controls

## 1. Enforce Password & Lockout Policies
**Process:**
- Local Security Policy → Account Policies  
- Configure lockout threshold, duration, and password complexity  

## 2. Enable Credential Guard & LSA Protection
**Process:**
- Same process as Windows 11  
- Strongly recommended for domain controllers  

## 3. Disable SMBv1 and Harden SMB
**Process:**
- PowerShell:  
  - `Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol`  
- Enable SMB signing via GPO  

## 4. Apply ASR Rules
**Process:**
- Use Defender ASR PowerShell commands  
- Apply server‑specific rules (block lateral movement)  

## 5. Enable BitLocker
**Process:**
- Use TPM + PIN for DCs  
- PowerShell:  
  - `Enable-BitLocker -MountPoint "C:" -EncryptionMethod XtsAes256`  

## 6. Harden Windows Firewall
**Process:**
- Default deny inbound  
- Allow only required server roles  
- Use GPO for consistency  

## 7. Remove Unnecessary Roles & Features
**Process:**
- Server Manager → Remove Roles  
- PowerShell:  
  - `Uninstall-WindowsFeature <role>`  

## 8. Enable Exploit Protection
**Process:**
- Configure via Windows Security  
- Export/import XML for consistency  

## 9. Configure Sysmon + Central Logging
**Process:**
- Install Sysmon with SwiftOnSecurity config  
- Configure Windows Event Forwarding to SIEM  

## 10. Harden PowerShell
**Process:**
- Enable logging  
- Restrict remote PowerShell  
- Enforce Constrained Language Mode  

## 11. Secure Administrative Access
**Process:**
- Use PAWs  
- Restrict RDP to admin group  
- Enforce NLA  

## 12. Enable Network Level Authentication (NLA)
**Process:**
- System Properties → Remote → Require NLA  
- Or via GPO  

## 13. Implement Least Privilege
**Process:**
- Audit local admin group  
- Restrict service account permissions  
- Use GPO to enforce rights  

## 14. Harden Scheduled Tasks
**Process:**
- Audit tasks: `schtasks /query /fo LIST /v`  
- Restrict who can create tasks  
- Remove unknown tasks  

## 15. Enable File Integrity Monitoring
**Process:**
- Use Sysmon rules  
- Enable auditing on sensitive directories  
- Forward logs to SIEM  
