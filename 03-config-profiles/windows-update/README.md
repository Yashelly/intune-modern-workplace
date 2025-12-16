# Windows Update – Enterprise Baseline

## Overview
This configuration defines an **enterprise-grade Windows Update for Business (WUfB) baseline** for Windows devices managed via Microsoft Intune.

The goal of this baseline is to ensure timely installation of security and quality updates while maintaining device stability, predictable user experience, and controlled feature adoption.

---

## Scope
- **Platform:** Windows 10 and later  
- **Workload:** Windows Update for Business  
- **Profile type:** Update ring  
- **Assignment model:** Device-based  
- **Target devices:** Autopilot-enrolled Windows devices  

---

## Update strategy

### Production update ring
The update ring is configured with the following principles:

- Security and quality updates are installed automatically with a short deferral
- Feature updates are deferred to reduce the risk of instability
- Automatic upgrade to the latest Windows 11 release is disabled
- Driver updates are allowed
- Rollback window for feature updates is preserved
- No forced reboot deadlines are enforced

This approach balances security, stability, and user productivity, making it suitable for the majority of enterprise-managed devices.

---

## User experience considerations
- Updates are installed automatically during maintenance time
- Active hours are respected to avoid disruptive restarts
- Users are allowed to pause updates and manually check for updates
- Default Windows update notifications are used

Aggressive deadline-based enforcement is intentionally avoided in this baseline to reduce unnecessary user disruption.

---

## Intentionally not configured
The following settings are intentionally left not configured:

- Pre-release / Insider builds
- Deadline-based update enforcement
- Forced reboot behavior

These controls are typically introduced only in tightly regulated or high-maturity environments and are not required for a standard enterprise baseline.

---

## Assignment strategy
This update ring is assigned to **Autopilot-enrolled devices** to ensure update policies are applied consistently from the initial provisioning stage.

User-based assignments are intentionally avoided to maintain a clear and predictable **device-scoped update model**.

---

## Evidence
Configuration and assignment evidence is available in the `screenshots` folder:
- `windows-update_ring_review_summary.png`

---

## Design principles
- Security-first, stability-focused
- Controlled feature adoption
- Minimal user disruption
- Device-based targeting
- Alignment with enterprise Windows Update best practices
