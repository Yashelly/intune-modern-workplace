# Application Management (Microsoft Intune)

This section demonstrates enterprise-style application management using Microsoft Intune, covering different application types and deployment scenarios.

The goal is to show how mandatory and optional applications are delivered to Autopilot-enrolled devices in a controlled and structured way.

---

## Application Scenarios Covered

### 1. Microsoft 365 Apps (Built-in)
Core productivity baseline deployed using the built-in Intune application.

- Application type: Built-in Microsoft 365 Apps
- Deployment model: Device-based
- Assignment: Required → Intune_Devices_Autopilot
- Tracked during Enrollment Status Page (ESP)

This represents a mandatory corporate productivity baseline available on all managed devices.

---

### 2. Zoom (Win32 - Corporate)
Line-of-business collaboration application packaged and deployed as a Win32 app.

- Application type: Win32
- Packaging: IntuneWinAppUtil (.intunewin)
- Deployment model: Device-based
- Assignment: Required → Intune_Devices_Autopilot
- Detection: File-based detection rule

This demonstrates enterprise Win32 application packaging, detection logic, and lifecycle management.

---

### 3. Telegram Desktop (Microsoft Store app - Optional)
Optional end-user application delivered via Microsoft Store integration.

- Application type: Microsoft Store app (new)
- Deployment model: User-driven (self-service)
- Assignment: Available for enrolled devices → Intune_Devices_Autopilot

This scenario demonstrates optional software distribution via Company Portal without forcing installation.

---

## Design Principles

- Device-based assignments for mandatory applications
- User-driven installation for optional software
- Clear separation between built-in, Win32, and Store application types
- Minimal but sufficient configuration to reduce deployment complexity