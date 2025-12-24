# CA – Require MFA

## Purpose
Enforce multi-factor authentication for interactive access to
corporate cloud applications.

This control mitigates risks associated with compromised credentials
by requiring a second authentication factor during sign-in.

---

## Scope & Targeting
- **Users:** All users  
  - **Excluded:** Break-glass account
- **Target resources:** All cloud apps
- **Network:** Not configured

Conditional Access is evaluated at user sign-in time,
therefore the policy is intentionally scoped at the **user level**.

---

## Control Logic
Access is granted only after successful completion of a
multi-factor authentication challenge.

Configured grant control:
- Require multi-factor authentication

Authentication strength is not used in this policy to maintain
compatibility with existing MFA methods.

---

## Design Considerations / Trade-offs
- MFA enforcement is independent from device compliance controls
- Break-glass exclusion ensures recoverability during access control incidents
- Additional risk-based or context-based controls can be layered separately

---

## Evidence
The following evidence demonstrates policy configuration and enforcement:

1. **Policy overview (scope and targeting)**  
   `01-policy-overview.png`

2. **Grant controls – Require MFA**  
   `02-grants.png`

3. **Sign-in log – MFA successfully enforced**  
   `03-sign-in-log-mfa-success.png`

---

## Result
All user sign-ins to cloud applications require multi-factor authentication,
significantly reducing the risk of unauthorized access.
