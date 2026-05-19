# Windows 11 Incident Response Case Study: Infatica P2B Proxy Agent (March 2026)

## Overview
In March 2026, unusual network activity was detected on a Windows 11 Pro workstation. A routine `netstat -ano` review revealed a large number of persistent outbound connections to foreign IP addresses on TCP port **8886**, a port not used by Windows or any legitimate applications installed on the system.

Further investigation identified the responsible process as:

```
infatica_agent.exe
```

This executable was not recognized by the user and did not correspond to any expected software. The process was later confirmed to be part of **Infatica P2B**, a residential proxy agent that routes third‑party traffic through the user’s machine. The agent automatically relaunched after reboot, indicating a persistence mechanism.

This report documents the detection, investigation, containment, eradication, and hardening actions taken.

---

## Initial Detection
The user executed:

```
netstat -ano
```

The output showed:

- Normal Windows system ports  
- Expected gaming ports (Steam/Epic/GOG)  
- MySQL listening on 3306/33060  
- mDNS and WS‑Discovery traffic (expected due to HP printer and Adobe Reader)  
- **Dozens of outbound connections to port 8886** from a single PID  

Example suspicious entries:

```
192.168.x.x:52465 → 95.173.204.44:8886 ESTABLISHED PID 30724
192.168.x.x:52478 → 162.244.34.4:8886 ESTABLISHED PID 30724
192.168.x.x:52484 → 185.223.94.98:8886 ESTABLISHED PID 30724
```

Port 8886 is not associated with:

- Windows  
- Steam/Epic/GOG  
- Adobe Reader  
- HP printers  
- GitHub  
- Edge browser  

This pattern indicated a likely unwanted or malicious network component.

---

## Process Identification
The suspicious PID was identified using:

```
tasklist /FI "PID eq 30724"
```

Result:

```
infatica_agent.exe           30724 Console    1    16,244 K
```

This confirmed the process name and that it was running under the user session.

---

## Containment Attempt
The process was terminated:

```
taskkill /PID 30724 /F
```

The kill succeeded, and the process did not immediately respawn.

A service check showed no registered Windows service:

```
sc delete infatica
[SC] OpenService FAILED 1060: The specified service does not exist as an installed service.
```

A process check confirmed it was gone:

```
tasklist | findstr infatica
```

No results.

---

## Persistence Discovery
After reboot, the process returned:

```
infatica_agent.exe           15172 Console    1    8,036 K
```

This confirmed the presence of a persistence mechanism.

The executable path was then identified:

```
wmic process where "name='infatica_agent.exe'" get ProcessId,ExecutablePath
```

Result:

```
C:\Program Files (x86)\Infatica P2B\infatica_agent.exe
```

This confirmed that Infatica was installed as a full application under Program Files (x86), not as a temporary file or browser extension.

---

## Eradication

### 1. Kill the Running Process

```
taskkill /PID 15172 /F
```

### 2. Delete the Installation Directory

```
Remove-Item "C:\Program Files (x86)\Infatica P2B" -Recurse -Force
```

### 3. Search for Persistence Artifacts

Registry searches:

```
reg query HKCU /f "Infatica" /s
reg query HKLM /f "Infatica" /s
reg query HKCU /f "P2B" /s
reg query HKLM /f "P2B" /s
```

Startup folders:

```
C:\Users\<user>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup
```

Run keys:

```
reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Run
reg query HKLM\Software\Microsoft\Windows\CurrentVersion\Run
```

Scheduled tasks:

```
schtasks /query /fo LIST /v | findstr /i "infatica"
```

No remaining persistence entries were found.

### 4. Block the Infatica Port

```
New-NetFirewallRule -DisplayName "Block Port 8886" -Direction Outbound -RemotePort 8886 -Protocol TCP -Action Block
```

### 5. Reboot and Verify
After reboot:

```
tasklist | findstr infatica
netstat -ano | findstr 8886
```

No results were returned, confirming successful eradication.

---

## Post‑Incident Hardening

### MySQL Hardening (Local Only)
MySQL was listening on all interfaces:

```
0.0.0.0:3306
0.0.0.0:33060
```

Since MySQL is only used locally, the configuration was updated:

```
bind-address=127.0.0.1
```

Service restarted:

```
net stop mysql
net start mysql
```

### SMB Hardening
The workstation only connects outbound to a file server and does not host shares.

Inbound SMB rules were disabled:

- File and Printer Sharing (SMB-In)  
- NB-Session-In  
- NB-Datagram-In  

### Browser Extension Audit
Extensions were reviewed in Edge and other browsers to ensure no proxy‑related add‑ons were present.

### Startup and Run Key Audit
All startup entries and Run keys were reviewed to confirm no hidden launchers remained.

---

## Root Cause Analysis
The system was running **Infatica P2B**, a residential proxy agent that:

- Routes third‑party traffic through the user’s IP  
- Maintains persistent outbound connections  
- Uses stealthy persistence mechanisms  
- Is often bundled with free software or installers  

The user did not knowingly install this software.

Although not traditional malware, the agent exposed the system to significant risks:

- Bandwidth hijacking  
- IP reputation damage  
- Potential legal exposure  
- Uncontrolled foreign traffic routing  

---

## Lessons Learned
- Routine netstat checks can reveal hidden network activity.  
- Non‑service persistence can hide in Program Files without obvious startup entries.  
- Outbound port anomalies are strong indicators of compromise.  
- Residential proxy agents behave similarly to malware in terms of persistence and network behavior.  
- Hardening MySQL and SMB reduces attack surface after cleanup.  

---

## Final Status
The Infatica P2B agent was:

- Identified  
- Contained  
- Removed  
- Verified eradicated  
- Prevented from returning via firewall rules  

The system is now clean and hardened.

---

## Repository Placement

This incident is a **security investigation and remediation case study** and belongs in:

security-findings/case-studies/windows-infactica-2026/Windows-11-Incident-Response-Case-1.md
