# CA – Block Legacy Authentication

## Purpose
Block legacy authentication protocols that do not support modern
security controls such as MFA, Conditional Access evaluation,
and device-based access enforcement.

This control reduces the attack surface by eliminating
password-based authentication methods commonly targeted
by credential-stuffing and password-spray attacks.

---

## Scope & Targeting
- **Users:** All users  
  - **Excluded:** Break-glass account
- **Target resources:** All cloud apps
- **Network:** Not configured

Conditional Access is evaluated at user sign-in time.
A dedicated break-glass account is excluded to prevent
administrative lockout scenarios.

---

## Control Logic
The policy blocks sign-in attempts using **legacy authentication clients** only.

Configured client apps:
- Exchange ActiveSync clients
- Other legacy authentication clients

Modern authentication flows (browser, modern desktop and mobile clients)
are intentionally **not affected** by this policy.

---

## Design Considerations / Trade-offs
- Blocking legacy authentication is a prerequisite for
  effective Conditional Access and MFA enforcement
- Some legacy applications may require remediation or replacement
- Break-glass exclusion ensures recoverability during identity incidents

---

## Evidence
The following evidence demonstrates policy configuration and enforcement intent:

1. **Policy overview (scope, grant, exclusions)**  
   `01-policy-overview.png`

2. **Legacy authentication client conditions**  
   `02-conditions.png`

---

## Result
Legacy authentication protocols are blocked across the tenant,
significantly reducing exposure to credential-based attacks.
