# LAB-08 — Windows Firewall

## Objective

Configure Windows Firewall through Microsoft Intune to establish a secure inbound network baseline for Windows 11 devices.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

A Windows Firewall policy was created in Microsoft Intune and assigned to the `MD102-Pilot-Users` group.

The policy configured Windows Firewall for the following network profiles:

* Domain
* Private
* Public

Firewall protection was enabled for all three profiles.

## Inbound Traffic

The default inbound action was changed from:

`Allow`

to:

`Block`

This establishes a secure-by-default firewall posture where unsolicited inbound traffic is blocked unless explicitly permitted by an applicable firewall rule.

## Configuration Summary

| Setting                | Configuration        |
| ---------------------- | -------------------- |
| Domain Firewall        | Enabled              |
| Private Firewall       | Enabled              |
| Public Firewall        | Enabled              |
| Default Inbound Action | Block                |
| Assignment             | `MD102-Pilot-Users`  |
| Platform               | Windows 10 and later |

## Validation

The policy was created successfully and assigned to the MD-102 pilot environment.

The Windows Firewall configuration was later validated on the Windows 11 test VM using the Windows Firewall management interface.

The firewall state was confirmed as **On**.

## Skills Demonstrated

* Microsoft Intune Windows Firewall policy management
* Windows network profile security
* Inbound firewall configuration
* Secure-by-default endpoint configuration
* Policy assignment to pilot users
* Endpoint security validation

## Outcome

LAB-08 established a baseline Windows Firewall configuration for the MD-102 pilot environment.

The configuration provides a foundation for the following lab, which introduces an explicit inbound firewall rule for Remote Desktop.
