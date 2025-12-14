# Compliance Policies

## Overview
Compliance policies are used to evaluate the security and health state of managed Windows devices in Microsoft Intune.

These policies do not configure devices directly. Instead, they assess whether devices meet defined security requirements and report compliance status, which is later enforced through Conditional Access.

---

## Windows Compliance – Baseline

**Purpose:**  
Define baseline security and health requirements for Windows 10/11 devices before granting access to corporate resources.

**Configuration:**
- Platform: Windows 10 and later
- Disk encryption (BitLocker): Required
- Secure Boot: Required
- Trusted Platform Module (TPM): Required
- Firewall: Required
- Password protection: Enforced
- Microsoft Defender Antivirus:
  - Real-time protection required
  - Security intelligence up-to-date
- Microsoft Defender for Endpoint:
  - Device risk score ≤ Medium
- Minimum OS version enforced

**Result:**  
Devices that do not meet the baseline security requirements are marked as non-compliant and are restricted from accessing corporate resources when used with Conditional Access.

**Evidence:**
- `windows-compliance-baseline/01-policy-overview.png`
- `windows-compliance-baseline/02-device-health-os.png`
- `windows-compliance-baseline/03-system-security-defender.png`
- `windows-compliance-baseline/04-assignments.png`
