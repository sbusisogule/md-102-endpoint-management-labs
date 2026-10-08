# LAB-13 — Windows BitLocker

## Objective

Configure Windows BitLocker through Microsoft Intune to establish a managed disk-encryption baseline for Windows 11 devices.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

A Windows encryption policy was created in Microsoft Intune as part of the endpoint security baseline.

The policy was assigned to the `MD102-Pilot-Users` group for pilot testing.

BitLocker was used to demonstrate centrally managed Windows device encryption and the protection of data stored on the endpoint.

## Security Context

BitLocker provides volume-level encryption for Windows devices.

In an enterprise environment, managing BitLocker through Intune allows administrators to standardize encryption settings and integrate device encryption into the broader endpoint-security strategy.

The configuration complements other controls implemented during the MD-102 labs, including:

* Windows Firewall
* Microsoft Defender Antivirus
* Windows LAPS
* Windows Hello for Business
* Compliance policies
* Conditional Access

## Assignment

| Item        | Configuration                  |
| ----------- | ------------------------------ |
| Policy Type | Windows encryption / BitLocker |
| Assignment  | `MD102-Pilot-Users`            |
| Test Device | `INTUNE-USER`                  |
| Platform    | Windows 10 and later           |

## Validation

The BitLocker policy was created and assigned in Microsoft Intune.

The configuration was reviewed as part of the Windows endpoint security policy set.

Intune policy reporting can take time to update, so the lab was documented based on the configured policy rather than waiting for delayed reporting.

## Skills Demonstrated

* Microsoft Intune encryption policy management
* Windows BitLocker concepts
* Endpoint data protection
* Security baseline configuration
* Intune group assignments
* Enterprise device-management practices

## Outcome

LAB-13 demonstrated how BitLocker can be incorporated into an enterprise Windows endpoint-management strategy using Microsoft Intune.

The lab established the foundation for centrally managed disk encryption and reinforced the importance of protecting data at rest on managed Windows devices.
