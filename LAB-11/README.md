# LAB-11 — Windows Autopilot Deployment Profile

## Objective

Configure and evaluate a Microsoft Windows Autopilot deployment profile for user-driven Windows 11 deployment and Microsoft Entra join.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows Autopilot
* Windows 11 Enterprise
* Pilot environment: `MD102-Pilot-Users`

## Configuration

An existing Windows Autopilot deployment profile was reviewed as part of the MD-102 endpoint-management environment.

### Deployment Profile

| Setting          | Configuration                      |
| ---------------- | ---------------------------------- |
| Profile Name     | `LAB 11WIN11 Autopilot UserDriven` |
| Deployment Mode  | User-Driven                        |
| Join Type        | Microsoft Entra joined             |
| Assignment       | 1 group                            |
| Assigned Devices | 0                                  |
| Created          | 2026-10-01                         |

The profile is designed for a user-driven Windows deployment in which the device joins Microsoft Entra ID and is subsequently managed through Microsoft Intune.

## Enrollment Status Page

The Microsoft Intune Enrollment Status Page (ESP) was also reviewed.

The existing default ESP configuration was retained rather than creating or modifying a tenant-wide replacement profile.

This demonstrated the relationship between an Autopilot deployment profile and the Enrollment Status Page during Windows provisioning.

## Autopilot Device Status

The Windows Autopilot Devices page was reviewed.

At the time of testing:

* Autopilot settings were not found.
* Last successful sync: Never.
* Last sync request: Never.

The existing deployment profile was therefore documented without making unnecessary tenant-wide changes.

## Validation

The Autopilot deployment profile configuration was reviewed in Microsoft Intune.

The lab environment already contained a Windows 11 device that was successfully Microsoft Entra joined and Intune managed. This provided a reference point for the desired endpoint-management state.

However, the Autopilot device-registration and deployment workflow itself was **not fully validated** because the tenant's Autopilot device synchronization had not completed.

The successful Entra join and Intune enrollment of `INTUNE-USER` should therefore not be interpreted as proof that Autopilot performed the enrollment.

## Skills Demonstrated

* Windows Autopilot concepts
* Intune Autopilot deployment profiles
* User-driven deployment
* Microsoft Entra join
* Enrollment Status Page concepts
* Autopilot device registration and synchronization
* Safe management of tenant-wide enrollment settings
* Distinguishing profile configuration from deployment validation

## Outcome

LAB-11 demonstrated how a Windows Autopilot deployment profile is configured and how it relates to Microsoft Entra join, Intune enrollment, and the Enrollment Status Page.

The existing tenant configuration was preserved without unnecessary changes to the default Enrollment Status Page or creation of duplicate Autopilot profiles.

## Evidence Status

**Status: Configured / Not End-to-End Validated**

The deployment profile configuration was validated. Actual Autopilot device registration, synchronization, and end-to-end OOBE deployment were not validated.
