# Conditional Access

## Overview
Conditional Access policies are used to enforce Zero Trust access controls for cloud resources in Microsoft Entra ID.

This configuration focuses on:
- Multi-factor authentication (MFA) enforcement
- Blocking legacy authentication
- Device-based access control using Intune compliance
- Secure emergency access via break-glass account

---

## Break-glass account
A dedicated break-glass account is created to ensure administrative access in case Conditional Access policies block standard admin accounts.

**Design decisions:**
- Separate cloud-only account
- Excluded from all Conditional Access policies
- Assigned Global Administrator role
- Used only for emergency access

**Evidence:**
- `01-breakglass_user_created.png`
- `02-breakglass_role_assignment.png`

---

## CA – Require MFA

**Purpose:**  
Enforce multi-factor authentication for all users accessing cloud applications.

**Configuration:**
- Users: All users  
- Exclusions: Break-glass account  
- Target resources: All cloud apps  
- Grant: Require multi-factor authentication  
- Policy state: Enabled

**Result:**  
MFA challenge is enforced during sign-in.

**Evidence:**
- `01-ca_policy01_require_mfa_overview.png`
- `02-ca_policy01_require_mfa_grant.png`
- `03-sign-inlog_ca_require_mfa_applied.png`

---

## CA – Block Legacy Authentication

**Purpose:**  
Prevent authentication methods that do not support modern security controls.

**Configuration:**
- Users: All users  
- Target resources: All cloud apps  
- Client apps:
  - Exchange ActiveSync clients
  - Other legacy authentication clients
- Grant: Block access  
- Policy state: Enabled

**Result:**  
Legacy authentication protocols are blocked.

**Evidence:**
- `01-ca_policy03_block_legacy_overview.png`
- `02-ca_policy03_block_legacy_conditions.png`

---

## CA – Require Compliant Device

**Purpose:**  
Ensure that access to corporate cloud resources is allowed only from Intune-compliant Windows devices.

**Configuration:**
- Users: All users  
- Exclusions: Break-glass account  
- Target resources: All cloud apps  
- Conditions: Windows devices  
- Grant: Require device to be marked as compliant  
- Policy state: Enabled

**Result:**  
Access is granted only if the device meets Intune compliance requirements.

---

## Policy export
All Conditional Access policies in this section are additionally exported in JSON format for reference and configuration traceability.

**Export file:**
- `json/ca_policies_export.json`

