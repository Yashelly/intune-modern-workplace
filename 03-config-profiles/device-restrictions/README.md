# Device Restrictions – Enterprise Baseline

## Overview
This configuration profile defines an enterprise-grade **Device Restrictions baseline** for Windows endpoints managed via Microsoft Intune.

The primary goal of this profile is to:
- Reduce attack surface
- Disable consumer-oriented features
- Enforce basic credential hygiene
- Preserve user productivity
- Avoid overlap with Endpoint Security, Compliance, and Defender workloads

The profile is intentionally scoped and minimal, following modern enterprise and Zero Trust design principles.

---

## Scope
- **Platform:** Windows 10 and later  
- **Profile type:** Device restrictions  
- **Assignment model:** Device-based  
- **Target devices:** Autopilot-enrolled Windows devices  

---

## Configured areas

### App Store
- Developer unlock is blocked to prevent unnecessary developer capabilities on standard user devices.

This helps reduce potential attack surface while keeping application deployment fully managed through Intune.

---

### Password
A baseline password policy is enforced to ensure basic credential hygiene:
- Password requirement enabled
- Alphanumeric password type
- Minimum password length enforced
- Automatic screen lock after inactivity
- Password expiration configured
- Simple passwords blocked

The configuration avoids aggressive or disruptive controls (such as automatic device wipe thresholds) to prevent accidental data loss in enterprise environments.

---

### Privacy
- Consumer-focused privacy experience is disabled
- Input personalization is disabled

These settings minimize unnecessary data collection while keeping application-level permissions flexible and business-friendly.

---

### Microsoft Defender SmartScreen
- Protection against malicious websites enabled
- Blocking of unverified file downloads enabled

SmartScreen is used as a **baseline protection layer** and complements Microsoft Defender without duplicating Endpoint Security policies.

---

### Windows Spotlight
All Windows Spotlight and consumer-related features are disabled:
- Spotlight content
- App suggestions
- Welcome and promotional experiences

This ensures a clean, distraction-free enterprise user experience.

---

## Intentionally not configured
The following areas are intentionally left **not configured** to avoid policy overlap, user disruption, or legacy management patterns:

- Start menu layout and personalization
- Search behavior
- Reporting and telemetry
- Network, printer, and projection settings
- Power settings
- Microsoft Defender Antivirus (managed via Endpoint Security)
- Per-app privacy permissions
- Cloud and connectivity-related restrictions

These settings are better handled through dedicated Intune workloads, Settings Catalog, or Defender policies when required by specific use cases.

---

## Assignment strategy
This profile is assigned to **Autopilot-enrolled devices** to ensure the baseline configuration is applied consistently during initial device provisioning.

User-based assignments are intentionally avoided to maintain a clear and predictable **device-scoped configuration model**.

Applicability rules are not used, as targeting is fully handled through device group assignments.

---

## Evidence
Screenshots demonstrating the configuration and assignment are available in the `screenshots` folder:
- `device-restrictions_review_summary.png`
- `device-restrictions_review_summary_assignments.png`

---

## Design principles
- Minimal and intentional configuration
- No legacy or kiosk-style enforcement
- Clear separation of responsibilities between Intune workloads
- Enterprise-first, user-respecting approach
