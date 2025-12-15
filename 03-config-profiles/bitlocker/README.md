# BitLocker

## Overview

This section documents an enterprise BitLocker baseline implemented via **Microsoft Intune Configuration Profiles** using the **Settings Catalog**.

The configuration enforces modern **device encryption during provisioning**, ensures secure recovery key handling through Microsoft Entra ID, and avoids user interaction to support scalable enterprise deployments.

---

## Policy: CP – BitLocker – Enterprise Baseline

### Platform
- Windows 10 and later

### Deployment method
- Intune Configuration Profile
- Settings Catalog (modern device encryption)

---

## Configuration highlights

- **Require device encryption:** Enabled  
- **Silent encryption during Autopilot provisioning** (TPM-based, no user interaction)
- **Compatible with Entra ID join and Autopilot scenarios**
- **Minimal configuration surface** to reduce complexity and deployment risk

---

## Design decisions

- Device encryption is enforced using the modern Settings Catalog approach instead of legacy BitLocker templates.
- Startup authentication relies on TPM-only to enable silent encryption without requiring user input.
- Advanced BitLocker options (such as removable drive enforcement or write-blocking) are intentionally left not configured to avoid unnecessary disruption and align with enterprise baseline best practices.
- The policy is scoped to **Autopilot-enrolled devices** to ensure encryption is applied at provisioning time rather than post-deployment.

---

## Evidence

- `screenshots/bitlocker_policy_overview.png`
