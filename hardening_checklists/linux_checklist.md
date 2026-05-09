# Linux Hardening Checklist — Top 15 Critical Controls

## 1. Enforce Strong Authentication
**Process:**
- Edit `/etc/login.defs` to configure password aging (`PASS_MAX_DAYS`, `PASS_MIN_DAYS`)  
- Install `libpam-pwquality` and edit `/etc/pam.d/common-password`  
- Add MFA:  
  - Install `google-authenticator`  
  - Configure `/etc/pam.d/sshd` with `auth required pam_google_authenticator.so`  

## 2. Disable Unnecessary Services
**Process:**
- List services: `systemctl list-unit-files --type=service`  
- Disable: `systemctl disable --now <service>`  
- Mask dangerous services: `systemctl mask <service>`  

## 3. Enable a Host Firewall
**Process:**
- Ubuntu:  
  - `ufw enable`  
  - `ufw default deny incoming`  
- RHEL:  
  - `firewall-cmd --set-default-zone=drop`  
  - Add required ports with `firewall-cmd --add-service=<service>`  

## 4. Keep System Updated
**Process:**
- Debian/Ubuntu: `apt update && apt upgrade -y`  
- RHEL: `dnf update -y`  
- Enable unattended upgrades (`apt install unattended-upgrades`)  

## 5. Secure SSH Configuration
**Process:**
- Edit `/etc/ssh/sshd_config`:  
  - `PermitRootLogin no`  
  - `PasswordAuthentication no`  
  - `AllowUsers <youruser>`  
- Restart SSH: `systemctl restart sshd`  

## 6. Enable SELinux or AppArmor
**Process:**
- SELinux:  
  - Edit `/etc/selinux/config` → `SELINUX=enforcing`  
- AppArmor:  
  - `aa-enforce /etc/apparmor.d/*`  

## 7. Harden File Permissions
**Process:**
- Audit `/etc`: `find /etc -type f -perm /022`  
- Restrict logs: `chmod 600 /var/log/*`  
- Remove world-writable bits: `chmod o-w <file>`  

## 8. Enable Auditd
**Process:**
- Install: `apt install auditd` or `dnf install audit`  
- Enable: `systemctl enable --now auditd`  
- Add rules in `/etc/audit/rules.d/`  

## 9. Use Integrity Monitoring (AIDE)
**Process:**
- Install: `apt install aide`  
- Initialize: `aideinit`  
- Add cron job: `/etc/cron.daily/aide`  

## 10. Restrict Sudo Access
**Process:**
- Edit `/etc/sudoers` using `visudo`  
- Require passwords  
- Log all sudo commands with `Defaults logfile="/var/log/sudo.log"`  

## 11. Harden Kernel Parameters
**Process:**
- Edit `/etc/sysctl.conf`:  
  - `net.ipv4.conf.all.rp_filter=1`  
  - `net.ipv4.tcp_syncookies=1`  
- Apply: `sysctl -p`  

## 12. Disable USB/External Media
**Process:**
- Add to `/etc/modprobe.d/blacklist.conf`:  
  - `blacklist usb-storage`  

## 13. Protect Cron and Systemd Jobs
**Process:**
- Create `/etc/cron.allow` with approved users  
- Audit timers: `systemctl list-timers`  

## 14. Harden Network Services
**Process:**
- Enforce TLS in service configs  
- Disable weak ciphers in `/etc/ssl/openssl.cnf`  
- Bind services to localhost when possible  

## 15. Implement Malware/Threat Protection
**Process:**
- Install ClamAV: `apt install clamav`  
- Install Falco for runtime detection  
- Schedule regular scans  
