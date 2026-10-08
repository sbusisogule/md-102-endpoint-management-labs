# LAB-04 — Windows Hello for Business

## Objective

Configure and validate Windows Hello for Business on the Windows 11 test device managed by Microsoft Intune.

The purpose of this lab is to demonstrate passwordless authentication using a Windows Hello for Business PIN and to verify that the feature is available on a Microsoft Entra joined and Intune-managed Windows 11 device.

---

## Lab Scenario

The organization wants to improve Windows 11 authentication security by allowing users to authenticate using Windows Hello for Business instead of relying exclusively on traditional passwords.

The MD-102 pilot user is therefore configured to use Windows Hello for Business on the test device.

---

## Environment

| Component           | Configuration         |
| ------------------- | --------------------- |
| Identity platform   | Microsoft Entra ID    |
| Management platform | Microsoft Intune      |
| Operating system    | Windows 11 Enterprise |
| Windows version     | 25H2                  |
| OS build            | 26200.6584            |
| Test device         | INTUNE-USER           |
| Test user           | MD102 Test User       |
| Assignment group    | MD102-Pilot-Users     |

---

## Windows Hello for Business Configuration

Windows Hello for Business was enabled for the test environment.

The Windows Hello for Business user state was confirmed as:

**Windows Hello for Business (User): True**

This indicated that Windows Hello for Business was available for the test user.

---

## PIN Enrollment

The test user completed Windows Hello for Business PIN enrollment on the Windows 11 test device.

The PIN was successfully created through:

**Settings → Accounts → Sign-in options**

After enrollment, Windows displayed Windows Hello PIN management options.

The device subsequently showed:

* **Change PIN**
* **I forgot my PIN**

These options confirmed that a Windows Hello PIN credential had been successfully provisioned for the user.

---

## Authentication Flow

The resulting authentication architecture can be represented as:

```text
MD102 Test User
       |
       v
Microsoft Entra ID
       |
       v
Windows 11 Enterprise
       |
       v
Windows Hello for Business
       |
       v
User PIN
       |
       v
Windows authentication
```

Windows Hello for Business provides a device-bound authentication experience rather than requiring the user to enter the account password for every Windows sign-in.

---

## Validation

The following validation was performed on `INTUNE-USER`:

### Windows Hello for Business

**User state:**

`True`

### Sign-in Options

The Windows 11 Sign-in options page displayed:

* Change PIN
* I forgot my PIN

The user successfully completed PIN enrollment.

This confirmed that Windows Hello for Business was operational for the test user.

---

## Security Concepts

Windows Hello for Business provides a more secure authentication model than relying solely on traditional passwords.

The authentication credential is associated with the Windows device and protected by the Windows security architecture.

The user's PIN is used to unlock the credential locally rather than functioning as the user's Microsoft Entra account password.

---

## Key Administration Concepts

### Passwordless Authentication

Windows Hello for Business supports modern authentication without requiring users to enter their traditional account password for Windows sign-in.

### PIN Authentication

The Windows Hello PIN is used locally on the enrolled device to unlock the user's Windows Hello credential.

The PIN should not be treated as simply another version of the user's Microsoft Entra password.

### Microsoft Entra Integration

Windows Hello for Business integrates with Microsoft Entra ID, allowing organizations to deploy modern authentication to managed Windows devices.

### Intune Management

Microsoft Intune can be used to configure and manage Windows Hello for Business settings across organizational Windows devices.

---

## Troubleshooting / Lessons Learned

The most important validation step was checking both the Windows Hello for Business user state and the actual Windows Sign-in options.

Checking only the Intune configuration does not prove that the user successfully completed enrollment.

A complete validation therefore involves:

1. Confirming Windows Hello for Business configuration.
2. Confirming the user is eligible for Windows Hello.
3. Completing PIN enrollment.
4. Verifying the PIN appears under Windows Sign-in options.
5. Confirming the user can manage the PIN.

---

## Relationship to Endpoint Security

Windows Hello for Business forms part of a broader endpoint security strategy.

In this lab environment it complements other controls implemented through the MD-102 labs, including:

* Microsoft Intune compliance
* Microsoft Entra Conditional Access
* Windows LAPS
* Microsoft Defender Antivirus
* Windows Firewall
* BitLocker
* Windows Update management

Together, these controls provide multiple layers of endpoint and identity protection.

---

## Outcome

Windows Hello for Business was successfully enabled for the test user.

The user completed PIN enrollment on the `INTUNE-USER` Windows 11 device.

The Windows Sign-in options page confirmed that the PIN credential was available for management.

---

## Skills Demonstrated

* Windows Hello for Business
* Passwordless authentication concepts
* Microsoft Entra authentication
* Microsoft Intune endpoint management
* Windows 11 Sign-in options
* PIN enrollment and management
* Endpoint authentication troubleshooting
* Modern identity security

---

## Lab Status

**Completed**

Test user:

`MD102 Test User`

Test device:

`INTUNE-USER`

Windows Hello for Business:

**Enabled**

PIN enrollment:

**Successfully completed**
