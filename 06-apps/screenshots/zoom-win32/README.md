# Zoom (Win32 - Corporate)

Line-of-business collaboration application deployed as a Win32 app via Microsoft Intune.

Implementation details:
- Packaging: IntuneWinAppUtil (.intunewin)
- Install command: ZoomInstallerFull.exe /silent
- Uninstall command: Installer.exe /uninstall /silent
- Detection: File exists (%ProgramFiles%\Zoom\bin\Zoom.exe)

Assignment:
- Required → Intune_Devices_Autopilot

This app demonstrates enterprise Win32 application packaging and lifecycle management.
