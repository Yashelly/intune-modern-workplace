# Enrollment Status Page (ESP)

## Overview
Enrollment Status Page (ESP) is configured to ensure that Windows devices are fully configured, secured, and ready before users can access the desktop during Windows Autopilot enrollment.

ESP prevents users from signing in to partially configured devices and enforces a predictable and secure onboarding experience.

## Design decisions
- ESP is enabled to block device usage until required apps and profiles are installed
- Both device and user phases are enforced to avoid incomplete enrollment
- Only a minimal, critical set of required applications is used to keep Autopilot reliable
- Installation errors do not allow bypass to maintain consistency and security
- Log collection is enabled to simplify troubleshooting

## Implementation
- Show app and profile installation progress: **Enabled**
- Block device use until apps and profiles are installed: **Enabled**
- Allow users to reset device if installation error occurs: **Disabled**
- Allow users to use device if installation error occurs: **Disabled**
- Block device until required apps are installed: **All**
- Install Windows updates during ESP: **Enabled**
- Assignment:
  - Dynamic device group: `Intune_Devices_Autopilot`

### Required applications
ESP enforces installation of all applications assigned as **Required** via Intune app assignments:
- Microsoft Store application (e.g. Microsoft 365 Apps / Company Portal)
- Win32 application (deployment validation scenario)

## Evidence
Screenshots demonstrating ESP configuration and required application assignments are available in the `screenshots/` folder.
