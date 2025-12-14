# Device Baseline – Windows (Enterprise)

## Overview
This configuration profile defines a core enterprise baseline for Windows devices.
It focuses on enforcing a clean corporate operating system experience by disabling
consumer Microsoft account usage, cloud-optimized content, and non-essential user feedback features.

The baseline is designed to be applied during Autopilot provisioning and serves as
a foundation for additional security and compliance policies.

---

## Accounts – Block Personal Microsoft Accounts

**Purpose:**  
Prevent the use of personal Microsoft accounts on corporate-managed Windows devices.

**Configuration:**
- Block adding non-Microsoft accounts manually
- Block Microsoft account connection
- Disable Microsoft Account Sign-In Assistant

**Result:**  
Only corporate Entra ID identities can be used on managed devices.

**Evidence:**
- `02-configuration_accounts_and_experience.png`

---

## Experience – Disable Consumer & Cloud Content

**Purpose:**  
Remove consumer-oriented features and cloud-driven content from the Windows user experience.

**Configuration:**
- Disable Windows Spotlight
- Disable cloud optimized content
- Disable consumer account state content
- Disable feedback notifications

**Result:**  
Devices present a clean, distraction-free enterprise Windows environment.

**Evidence:**
- `02-configuration_accounts_and_experience.png`

---

## Assignments

**Target group:**  
- `Intune_Devices_Autopilot`

**Result:**  
The baseline is applied automatically during device provisioning.

**Evidence:**
- `01-profile_overview_and_assignments.png`
