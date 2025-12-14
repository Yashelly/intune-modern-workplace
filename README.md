# Intune Modern Workplace

Reference implementation of a modern workplace environment using **Microsoft Intune** and **Microsoft Entra ID**.

Evidence is stored as screenshots and exported artifacts to keep the implementation verifiable and reproducible.

This repository is portfolio-oriented and contains documented configurations, screenshots as evidence, and JSON/PowerShell artifacts where export is supported.

## What’s covered
- Windows Autopilot (User-Driven, Microsoft Entra joined)
- Enrollment Status Page (ESP)
- Configuration profiles & compliance
- Endpoint Security (Defender, BitLocker)
- Conditional Access (Graph exports)
- Application management (Win32 / Store)
- Automation (PowerShell, Proactive Remediations)

## Repository structure
Each folder contains:

- `README.md` — Overview / Design decisions / Implementation
- `screenshots/` — evidence (portal views, status pages)
- `json/` — exported policies (when supported)
- `scripts/` — automation

## Notes
- Secrets are never committed (keys, tokens, certificates).
- Some objects (e.g., Autopilot profiles) may require Graph API to export.
