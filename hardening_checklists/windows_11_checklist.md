# Windows 11 Hardening Checklist — Top 15 Critical Controls

## 1. Enable Credential Guard
**Process:**
- Windows Security → Device Security → Core Isolation → Enable  
- Or via GPO:  
  - Computer Config → Admin Templates → System → Device Guard → Turn On Credential Guard  

## 2. Enable LSA Protection
**Process:**
- Registry:  
  - `HKLM\SYSTEM\CurrentControlSet\Control\Lsa` → `RunAsPPL=1`  
- Or via GPO:  
  - System → Local Security Authority → Configure LSASS  

## 3. Apply Attack Surface Reduction (ASR) Rules
**Process:**
- PowerShell:  
  - `Set-MpPreference -AttackSurfaceReductionRules_Ids <ID> -AttackSurfaceReductionRules_Actions Enabled`  

## 4. Enable Application Control
**Process:**
- Enable Smart App Control  
- Or create WDAC policies via `New-CIPolicy`  

## 5. Enable BitLocker
**Process:**
- Control Panel → BitLocker Drive Encryption  
- PowerShell:  
  - `Enable-BitLocker -MountPoint "C:" -EncryptionMethod XtsAes256`  

## 6. Harden Windows Firewall
**Process:**
- Set inbound default deny  
- PowerShell:  
  - `Set-NetFirewallProfile -Profile Domain,Public,Private -DefaultInboundAction Block`  

## 7. Disable Unnecessary Optional Features
**Process:**
- PowerShell:  
  - `Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol`  
  - Disable PowerShell 2.0  

## 8. Enable Exploit Protection
**Process:**
- Windows Security → App & Browser Control → Exploit Protection  
- Export/import configs via XML  

## 9. Configure Windows Defender
**Process:**
- Enable cloud protection  
- Enable tamper protection  
- PowerShell:  
  - `Set-MpPreference -MAPSReporting Advanced`  

## 10. Harden PowerShell
**Process:**
- Enable script block logging  
- Enable transcription  
- GPO: Admin Templates → Windows Components → PowerShell  

## 11. Secure Local Accounts
**Process:**
- Disable Guest  
- Rename Administrator  
- Enforce password policies via Local Security Policy  

## 12. Enable Advanced Logging
**Process:**
- Install Sysmon  
- Configure Windows Event Forwarding  
- Enable advanced audit policy  

## 13. Disable Unnecessary Startup Items
**Process:**
- Task Manager → Startup  
- Remove autoruns using Sysinternals Autoruns  

## 14. Reduce Telemetry
**Process:**
- Settings → Privacy → Diagnostics  
- GPO:  
  - Computer Config → Admin Templates → Windows Components → Data Collection  

## 15. Harden Browser Security
**Process:**
- Enable SmartScreen  
- Disable insecure extensions  
- Enforce download restrictions  
