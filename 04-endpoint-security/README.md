# 04-endpoint-security

## Overview

This section demonstrates an enterprise-grade endpoint security baseline implemented using **Microsoft Defender Antivirus** and **Attack Surface Reduction (ASR)** via **Microsoft Intune Endpoint Security**.

The configuration focuses on enforcing strong security controls, reducing attack surface, and preventing common enterprise attack vectors while avoiding unnecessary disruption.

---

## Microsoft Defender Antivirus

A centralized Microsoft Defender Antivirus policy is enforced via Intune Endpoint Security.

### Key security controls

- Real-time protection enabled  
- Cloud-delivered protection enabled  
- Behavior monitoring enabled  
- Network Protection enabled (**block mode**)  
- Potentially Unwanted Applications (PUA) protection enabled (**block mode**)  
- Cloud Block Level set to **High**  
- Local administrator Defender exclusions disabled  

### Design notes

- All critical protections are enforced in block mode.
- No antivirus exclusions are configured to avoid weakening endpoint protection.
- Advanced and legacy settings are intentionally left at Microsoft secure defaults.

### Evidence

- `defender/defender_av_policy_overview.png`

---

## Attack Surface Reduction (ASR)

An enterprise ASR baseline is deployed to reduce common attack techniques such as credential theft, Office abuse, LOLBins usage, lateral movement, and ransomware activity.

### Enforced ASR rules (Block)

- Credential theft from LSASS  
- Office applications creating child processes  
- Office macro Win32 API abuse  
- Obfuscated script execution  
- JavaScript/VBScript launching downloaded executables  
- Abuse of vulnerable signed drivers (BYOVD)  
- Persistence via WMI event subscription  
- Use of copied or impersonated system tools  
- Office process injection  
- Safe Mode reboot abuse  
- PSExec and WMI-based lateral movement  
- Advanced protection against ransomware  

### Audit-only rules

- Block executable content from email client and webmail  

### Exclusions

No Attack Surface Reduction (ASR) exclusions are configured.  
Other ASR rules are intentionally left not configured to avoid unnecessary disruption and align with enterprise baseline best practices.

### Evidence

- `asr/asr_policy_overview.png`
