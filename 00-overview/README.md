# Architecture Overview

This repository follows a **layered Modern Workplace architecture**
where each Intune workload has a **clear scope boundary**.

---

## Workload separation

| Area | Managed in |
|----|-----------|
| Device configuration | Configuration Profiles |
| Security controls | Endpoint Security |
| Compliance evaluation | Compliance Policies |
| Access enforcement | Conditional Access |
| Drift & health | Automation / Proactive Remediations |

This separation avoids:
- policy conflicts,
- unclear precedence,
- hidden side effects.

---

## Targeting model (high-level)

- **Device-based assignments** are preferred for baseline configuration
- **User-based assignments** are used only where required (e.g. CA)
- Production rollout assumes:
  - Pilot group
  - Production group
  - Explicit exclusions (break-glass)

Detailed targeting is documented per workload.

---

## Security boundaries

- Intune configures **endpoint posture**
- Compliance evaluates **device state**
- Conditional Access enforces **access decisions**
- No single policy is assumed to be “self-sufficient”

---

## Design trade-offs

Some controls are intentionally **not configured** to avoid:
- breaking user productivity,
- increasing support overhead,
- introducing lockout risks.

These decisions are documented per section.
