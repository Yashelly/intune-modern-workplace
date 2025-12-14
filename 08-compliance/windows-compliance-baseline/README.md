# Windows Compliance – Baseline

## Overview
This policy evaluates whether Windows devices meet baseline security and health requirements defined by the organization.

The compliance state is used as an access condition in Conditional Access policies.

---

## Policy Details

**Purpose:**  
Ensure that only secure and healthy Windows devices are allowed to access corporate cloud resources.

**Evaluated controls:**
- BitLocker disk encryption
- Secure Boot
- TPM availability
- Firewall enabled
- Password protection
- Microsoft Defender Antivirus health
- Microsoft Defender for Endpoint device risk score
- Minimum supported Windows version

---

## Outcome
Devices that fail one or more evaluated controls are marked as non-compliant.

When integrated with Conditional Access, non-compliant devices are blocked from accessing protected cloud resources.
