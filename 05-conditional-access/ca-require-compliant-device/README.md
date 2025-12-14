# CA – Require Compliant Device

**Purpose:**  
Ensure that only compliant Windows devices can access corporate cloud resources.

**Configuration:**
- Users: All users (excluding break-glass account)
- Target resources: All cloud apps
- Conditions: Windows devices
- Grant: Require device to be marked as compliant
- Policy state: Enabled

**Result:**  
Access is granted only from devices that meet Intune compliance requirements.
