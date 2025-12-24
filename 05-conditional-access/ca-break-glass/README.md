# Break-glass Account

## Purpose
Provide guaranteed emergency administrative access to the tenant
in case Conditional Access or identity controls block standard
administrative accounts.

The break-glass account is a critical safety mechanism and is not
intended for daily administrative use.

---

## Account Design
- **Account type:** Cloud-only user
- **User type:** Member
- **Display name:** breakglass
- **UPN:** Dedicated, non-personal account
- **Account state:** Enabled

The account is intentionally isolated from regular user workflows
and automation.

---

## Privileged Access
- **Directory role:** Global Administrator
- **Assignment type:** Direct
- **Scope:** Tenant-wide
- **Duration:** Permanent

The role assignment ensures full recovery capabilities
during identity or access control incidents.

---

## Conditional Access Exclusions
The break-glass account is explicitly excluded from:
- All Conditional Access policies
- Device compliance requirements
- MFA enforcement

This prevents administrative lockout scenarios
caused by misconfiguration or policy conflicts.

---

## Operational Use
- Used **only** for emergency access and recovery
- Not used for daily administration
- Access should be audited after each use
- Credentials stored securely and rotated periodically

---

## Evidence
The following evidence confirms account creation and privilege assignment:

1. **User creation (cloud-only account)**  
   `01-breakglass_user_created.png`

2. **Global Administrator role assignment**  
   `02-breakglass_role_assignment.png`
