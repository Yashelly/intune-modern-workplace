# Windows Autopilot — User-Driven (Entra ID Join)

## Overview
User-driven Windows Autopilot deployment for cloud-native modern workplace devices using Microsoft Entra ID.

## Design decisions
- User-Driven mode to support MFA and Conditional Access at sign-in
- Microsoft Entra ID Join to remove on-prem dependencies
- Standard user accounts for least privilege
- Dynamic device assignment for zero-touch provisioning
- Device naming based on serial number

## Implementation
- Deployment mode: User-Driven
- Join type: Microsoft Entra joined
- OOBE: Privacy, license, account options hidden
- Language: User select
- Device naming: DEV-%SERIAL%
- Assignment: Dynamic device group based on ZTDId attribute


## Evidence
See screenshots in `screenshots/`.
