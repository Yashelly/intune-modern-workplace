# Intune Modern Workplace – Enterprise Baseline (Portfolio)

This repository demonstrates a **practical Microsoft Intune / Modern Workplace baseline**
designed with **enterprise safety, workload separation, and operational maturity** in mind.

The goal is not to showcase every possible setting, but to demonstrate
**how decisions are made, scoped, targeted, and validated** in a real environment.

---

## Repository structure & navigation

| Folder | Purpose |
|------|--------|
| `00-overview` | Architecture principles, scope boundaries, and high-level design |
| `01-autopilot` | Device provisioning (Autopilot) |
| `02-esp` | Enrollment Status Page configuration |
| `03-config-profiles` | Configuration Profiles (non-security) |
| `04-endpoint-security` | Endpoint Security policies (Defender, BitLocker, ASR) |
| `05-conditional-access` | Conditional Access policies |
| `06-apps` | Application deployment (Win32, Store, Built-in) |
| `07-automation` | Scripts and Proactive Remediations |
| `08-compliance` | Compliance policies |
| `99-evidence` | Audit-ready screenshots and validation evidence |

---

## Design principles

- **Workload separation** is strictly respected  
  (Config Profiles ≠ Endpoint Security ≠ Compliance ≠ Conditional Access)
- **Least privilege & safe defaults** over aggressive hardening
- **Targeted assignments** over blanket "All users / All devices"
- **Operational safety** (no destructive actions, no lockout risks)
- **Evidence-driven configuration** (every critical decision is verifiable)

---

## What this repository is NOT

- Not a production-ready golden image
- Not a one-size-fits-all security baseline
- Not a full Zero Trust implementation

It is a **transparent, explainable baseline** suitable for enterprise environments.
