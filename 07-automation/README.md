# 07 – Automation

## Overview
This section contains **enterprise-grade automation** for Microsoft Intune–managed Windows endpoints.

The automation layer is intentionally split into two distinct models:
- **Standalone Intune scripts** for bulk or one-time remediation
- **Endpoint Analytics – Proactive Remediations** for continuous health monitoring

This separation reflects real-world enterprise practices and avoids overusing a single automation mechanism for all scenarios.

All scripts are designed to run in **SYSTEM context**.

---

## Automation models

### 1. Standalone scripts (`scripts/`)
Standalone PowerShell scripts intended for execution via **Microsoft Intune Scripts**.

**Use cases:**
- One-time or bulk remediation
- Incident response actions
- Initial device hardening
- Diagnostics and auditing tasks

**Characteristics:**
- Executed whenever assigned
- No external detection phase
- Explicit control over when and where they run

---

### 2. Proactive Remediations (`proactive-remediations/`)
Proactive Remediations implemented via **Endpoint Analytics**.

**Use cases:**
- Continuous device health monitoring
- Conditional remediation with minimal impact
- Preventive maintenance scenarios

**Characteristics:**
- Separate detection and remediation scripts
- Remediation runs only when an issue is detected
- Designed for long-term, low-noise enforcement

---

## Folder structure

```text
07-automation/
├─ scripts/                  # Standalone Intune scripts
│  ├─ templates/             # Reusable standalone script template
│  └─ *.ps1
│
├─ proactive-remediations/   # Endpoint Analytics Proactive Remediations
│  ├─ templates/             # Detect / remediate templates
│  ├─ timesync/              # Time synchronization health remediation
│  ├─ defender-signatures/   # Defender signature health remediation
│  └─ README.md
│
└─ README.md
