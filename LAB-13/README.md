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

The lab focused on the administrative configuration of BitLocker as a centrally managed Windows endpoint-security control.

## Security Context

BitLocker provides volume-level encryption for Windows devices.

In an enterprise environment, managing BitLocker through Intune allows administrators to establish standardized encryption requirements and incorporate disk encryption into the broader endpoint-security strategy.

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

The policy configuration was reviewed as part of the Windows endpoint-security policy set.

Intune reporting can take time to update. The lab therefore documents the configured policy and assignment rather than claiming successful endpoint application.

**Endpoint encryption status was not independently validated as part of this lab.**

The lab does not claim that:

* BitLocker was successfully enabled on `INTUNE-USER`
* A BitLocker recovery key was successfully escrowed
* Intune reported successful policy application

## Skills Demonstrated

* Microsoft Intune encryption policy management
* Windows BitLocker concepts
* Endpoint data protection
* Security baseline configuration
* Intune group assignments
* Enterprise device-management practices

## Outcome

LAB-13 demonstrated the configuration and assignment of a centrally managed BitLocker policy through Microsoft Intune.

The lab established the administrative foundation for managed Windows disk encryption while maintaining a clear distinction between policy configuration and endpoint-level validation.

## Evidence Status

**Status: Configured / Assignment Documented**

Endpoint encryption and recovery-key escrow were not independently validated in this lab.
