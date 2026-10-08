# LAB-22 — Windows Update Compliance

## Objective

Create a Microsoft Intune compliance policy that establishes a minimum supported Windows 11 operating-system version for the pilot environment.

## Environment

* Platform: Windows 11
* Management: Microsoft Intune
* Pilot group: `MD102-Pilot-Users`
* Test device: `INTUNE-USER`
* Current OS: Windows 11 25H2
* OS Build: `26200.6584`

## Compliance Policy

A Windows 10/11 compliance policy was created and assigned to the pilot group.

### Configuration

* Minimum OS version: `10.0.26200.0`
* System Security requirements: Not configured
* Microsoft Defender for Endpoint machine risk score: Not configured
* Windows Subsystem for Linux (WSL): Not configured
* Action for noncompliance: Mark device noncompliant immediately
* Assignment: `MD102-Pilot-Users`

## Validation

The policy was successfully created and assigned to the pilot group.

The compliance summary displayed:

* Compliant: `0`
* Noncompliant: `0`
* Others: `0`
* Total: `0`

No additional waiting was performed for Intune reporting to populate.

The test device was already running Windows 11 25H2 with OS Build `26200.6584`, which is above the configured minimum version of `10.0.26200.0`.

## Result

LAB-22 demonstrated the configuration of a Windows operating-system version compliance requirement in Microsoft Intune.

The policy establishes a minimum supported Windows version and defines immediate noncompliance for devices that do not meet the requirement.

## Evidence

Supporting material can be placed in:

* `Screenshots/`
* `Evidence/`

## Notes

The compliance report showed zero devices at the time of documentation. This is recorded as observed rather than interpreted as proof that the policy failed. The lab was considered complete without waiting for delayed Intune reporting.
