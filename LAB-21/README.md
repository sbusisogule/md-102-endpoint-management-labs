# LAB-21 — Windows 11 Feature Update

## Objective

Configure a Microsoft Intune feature update policy to manage the Windows 11 version deployed to pilot devices.

## Environment

* Platform: Windows 11
* Management: Microsoft Intune
* Pilot group: `MD102-Pilot-Users`
* Test device: `INTUNE-USER`
* Current Windows version: Windows 11 25H2
* OS Build: `26200.6584`

## Configuration

A Windows feature update policy was created in Microsoft Intune.

### Policy settings

* Target Windows version: Windows 11 25H2
* Rollout: `ImmediateStart`
* Deployment type: `Required`
* Assignment: `MD102-Pilot-Users`

## Validation

The test device was already running Windows 11 25H2 (OS Build `26200.6584`).

Because the device was already at the target feature-update version, no feature upgrade was required on the test device.

The lab therefore validated the configuration of the feature update policy and its intended targeting rather than demonstrating an actual version upgrade.

## Result

LAB-21 demonstrated how Microsoft Intune can be used to control Windows feature-update targeting for a pilot group.

The existing Windows 11 25H2 test device was already compliant with the targeted feature-update version.

## Evidence

Screenshots and additional evidence can be added to the following folders if available:

* `Screenshots/`
* `Evidence/`

## Notes

This lab intentionally does not claim that a feature update was installed during testing. The test device was already running the target Windows 11 25H2 release.
