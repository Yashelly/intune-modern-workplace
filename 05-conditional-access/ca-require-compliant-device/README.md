# CA – Require Compliant Device

## Purpose
Enforce access to corporate cloud resources by allowing sign-in **only from devices
that meet Microsoft Intune compliance requirements**.

This control ensures that access decisions are based on verified device posture,
not only on user identity or authentication strength.

---

## Scope & Targeting
- **Users:** All users  
  - **Excluded:** Break-glass account
- **Target resources:** All cloud apps
- **Platform:** Windows devices

Conditional Access is evaluated in the context of user sign-in,
therefore the policy is intentionally scoped at the **user level**.

---

## Control Logic
Access is granted only if the signing-in device:
- is enrolled in Microsoft Intune
- reports a **Compliant** state based on defined compliance policies

If the device is:
- not enrolled, or
- marked as **Non-compliant**

access is **denied**.

---

## Design Considerations / Trade-offs
- This policy intentionally blocks unmanaged or non-compliant devices
- Compliance evaluation is separated from MFA enforcement
- A dedicated break-glass account is excluded to prevent administrative lockout
- The effectiveness of this control depends on properly defined
  and monitored Intune compliance policies

---

## Evidence
The following evidence demonstrates policy intent, enforcement, and outcome:

1. **Policy overview (scope and targeting)**  
   `01-policy-overview.png`

2. **Grant controls – Require compliant device**  
   `02-grant-controls.png`

3. **Excluded users (break-glass)**  
   `03-exclusions.png`

4. **User-facing access denial (non-compliant device)**  
   `04-sign-in-result.png`

5. **Sign-in log – Conditional Access evaluation**  
   `05-sign-in-log-applied.png`

The sign-in log confirms that access was denied
because the device did not meet Intune compliance requirements.

---

## Result
Only devices that comply with Intune-defined compliance policies
are allowed to access corporate cloud resources.
