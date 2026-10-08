# LAB-05 — Windows LAPS

## Objective

Configure Windows Local Administrator Password Solution (Windows LAPS) through Microsoft Intune to manage the local administrator account on Windows 11 devices.

The purpose of this lab is to demonstrate how an endpoint administrator can automatically manage local administrator passwords and store the managed credentials in Microsoft Entra ID.

---

## Lab Scenario

The organization wants to reduce the security risk associated with shared or static local administrator passwords.

Windows LAPS is configured so that the local administrator password is:

* Automatically managed.
* Randomized.
* Complex.
* Rotated on a defined schedule.
* Backed up to Microsoft Entra ID.

The configuration is targeted at the MD-102 pilot group.

---

## Environment

| Component           | Configuration         |
| ------------------- | --------------------- |
| Management platform | Microsoft Intune      |
| Identity platform   | Microsoft Entra ID    |
| Operating system    | Windows 11 Enterprise |
| Windows version     | 25H2                  |
| OS build            | 26200.6584            |
| Test device         | INTUNE-USER           |
| Assignment group    | MD102-Pilot-Users     |
| LAPS solution       | Windows LAPS          |

---

## LAPS Policy

### Policy Name

`LAB-05-WIN-LAPS`

### Backup Directory

**Microsoft Entra ID only**

The local administrator password is configured to be backed up to Microsoft Entra ID.

### Password Age

**30 days**

The managed password is configured for rotation after the defined password age.

### Password Length

**16 characters**

### Password Complexity

The password is configured to use:

* Uppercase characters
* Lowercase characters
* Numbers
* Special characters

### Automatic Account Management

**Enabled**

The policy targets the built-in Windows administrator account.

### Administrator Account

**Built-in administrator**

### Password Suffix

A **random numeric suffix** configuration was used as part of the account management settings.

---

## Configuration Summary

| Setting                      | Configuration                                        |
| ---------------------------- | ---------------------------------------------------- |
| Backup directory             | Microsoft Entra ID only                              |
| Password age                 | 30 days                                              |
| Password length              | 16 characters                                        |
| Complexity                   | Uppercase, lowercase, numbers and special characters |
| Automatic account management | Enabled                                              |
| Target account               | Built-in administrator                               |
| Password suffix              | Random numeric suffix                                |

---

## Security Architecture

The LAPS workflow can be represented as:

```text id="zv1a6h"
Windows 11 Device
       |
       v
Microsoft Intune
       |
       v
Windows LAPS Policy
       |
       +---- Generate/manage local administrator password
       |
       v
Microsoft Entra ID
       |
       v
Protected LAPS password backup
```

This removes the need for administrators to maintain a common static local administrator password across multiple devices.

---

## Validation

The LAPS policy was created and assigned to:

`MD102-Pilot-Users`

The Windows LAPS configuration was also visible on the test device.

During command-line testing, the Windows LAPS PowerShell command was available:

```powershell
Get-LapsAADPassword
```

An attempt was made to retrieve the managed password from Microsoft Entra ID.

The command prompted for a device selection.

However, the password retrieval could not be completed because the Microsoft Graph PowerShell dependency was not installed in the test environment.

Therefore:

**LAPS configuration was validated, but actual password retrieval from Microsoft Entra ID was not validated.**

This distinction is intentionally documented rather than claiming a successful password retrieval that was not completed.

---

## PowerShell Testing

The following command was used during validation:

```powershell
Get-LapsAADPassword
```

An attempt was also made to use:

```powershell
Get-LapsAADPassword -Identity "Intune-User"
```

This failed because the `-Identity` parameter was not valid for the command in the installed environment.

The interactive `Get-LapsAADPassword` workflow subsequently prompted for a device identifier.

The command then indicated that Microsoft Graph PowerShell was required.

---

## Troubleshooting / Lessons Learned

This lab demonstrated that configuring Windows LAPS and retrieving a LAPS password are separate administrative tasks.

The configuration itself can be deployed through Intune, while password retrieval may require additional administrative tooling and permissions.

The following distinction was important:

```text id="e8qk6c"
LAPS Policy
    |
    v
Policy deployed
    |
    v
Password managed
    |
    v
Password backed up to Entra ID
    |
    v
Administrator retrieves password
```

Successful completion of the first stages does not automatically prove that the final retrieval workflow has been tested.

---

## Important Security Considerations

LAPS should be used to prevent local administrator passwords from being shared or reused across multiple endpoints.

Important security principles include:

* Use unique passwords per device.
* Rotate passwords regularly.
* Store passwords in a protected directory.
* Restrict password retrieval permissions.
* Audit administrator access to LAPS credentials.
* Avoid exposing managed administrator passwords unnecessarily.

Backing up passwords to Microsoft Entra ID allows organizations to manage the credentials centrally while applying appropriate access controls.

---

## Key Administration Concepts

### Windows LAPS

Windows LAPS automatically manages local administrator passwords on supported Windows devices.

### Microsoft Intune

Intune provides centralized policy deployment and management for Windows LAPS.

### Microsoft Entra ID

Microsoft Entra ID can be used as the backup directory for Windows LAPS credentials.

### Just-in-Time Credential Retrieval

Administrators can retrieve a managed local administrator password when required instead of maintaining a permanently known password.

---

## Outcome

The `LAB-05-WIN-LAPS` policy was successfully created and assigned to the MD-102 pilot group.

The configuration included:

* Microsoft Entra ID password backup.
* 30-day password rotation.
* 16-character passwords.
* Complex password requirements.
* Automatic account management.
* Built-in administrator targeting.

The LAPS configuration was validated on the test environment.

Actual password retrieval was **not fully validated** because Microsoft Graph PowerShell was not installed.

---

## Skills Demonstrated

* Windows LAPS administration
* Microsoft Intune policy configuration
* Microsoft Entra ID integration
* Local administrator account management
* Password rotation
* Password complexity management
* LAPS PowerShell troubleshooting
* Secure credential management
* Endpoint security administration

---

## Lab Status

**Completed**

Policy:

`LAB-05-WIN-LAPS`

Assignment:

`MD102-Pilot-Users`

Backup:

**Microsoft Entra ID only**

Password rotation:

**30 days**

Password length:

**16 characters**

Password retrieval:

**Configuration validated; retrieval not fully validated**
