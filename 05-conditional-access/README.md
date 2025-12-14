# Conditional Access

## Overview
Conditional Access policies are used to enforce Zero Trust access controls for cloud resources in Microsoft Entra ID.
This configuration focuses on MFA enforcement, legacy authentication blocking, and secure emergency access.

---

## Break-glass account
A dedicated break-glass account is created to ensure administrative access in case Conditional Access policies block standard admin accounts.

**Design decisions:**
- Separate cloud-only account
- Excluded from Conditional Access policies
- Assigned Global Administrator role
- Used only for emergency access

**Evidence:**
- `breakglass_user_created.png`
- `breakglass_role_assignment.png`

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
- `ca_policy01_require_mfa_overview.png`
- `ca_policy01_require_mfa_grant.png`
- `sign-inlog_ca_require_mfa_applied.png`

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
- `ca_policy03_block_legacy_overview.png`
- `ca_policy03_block_legacy_conditions.png`
