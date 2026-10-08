# LAB-11 — Windows Autopilot Deployment Profile

## Objective

Configure a Microsoft Windows Autopilot deployment profile for user-driven Windows 11 deployment and Microsoft Entra join.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows Autopilot
* Windows 11 Enterprise
* Pilot environment: `MD102-Pilot-Users`

## Configuration

An existing Windows Autopilot deployment profile was reviewed and used as part of the MD-102 endpoint-management environment.

### Deployment Profile

| Setting          | Configuration                      |
| ---------------- | ---------------------------------- |
| Profile Name     | `LAB 11WIN11 Autopilot UserDriven` |
| Deployment Mode  | User-Driven                        |
| Join Type        | Microsoft Entra joined             |
| Assignment       | 1 group                            |
| Assigned Devices | 0                                  |
| Created          | 2026-10-01                         |

The profile is designed for a user-driven Windows deployment where the device joins Microsoft Entra ID and is managed through Microsoft Intune.

## Enrollment Status Page

The Microsoft Intune Enrollment Status Page (ESP) was also reviewed.

The existing default ESP configuration was retained rather than creating or modifying a tenant-wide replacement profile.

This demonstrates the relationship between Windows Autopilot deployment profiles and the Enrollment Status Page during Windows provisioning.

## Autopilot Device Status

The Windows Autopilot Devices page was reviewed.

At the time of testing:

* Autopilot settings were not found.
* Last successful sync: Never.
* Last sync request: Never.

The existing deployment profile was therefore documented without making unnecessary tenant-wide changes.

## Validation

The Autopilot deployment profile configuration was reviewed in Microsoft Intune.

The lab environment already had a Windows 11 device that was successfully Microsoft Entra joined and Intune managed, providing a reference point for the desired endpoint-management state.

The Autopilot device-registration workflow itself was not treated as fully validated because the tenant's Autopilot device synchronization had not completed.

## Skills Demonstrated

* Windows Autopilot concepts
* Intune Autopilot deployment profiles
* User-driven deployment
* Microsoft Entra join
* Enrollment Status Page concepts
* Autopilot device registration and synchronization
* Safe management of tenant-wide enrollment settings

## Outcome

LAB-11 demonstrated how Windows Autopilot deployment profiles are configured and how they relate to Microsoft Entra join, Intune enrollment, and the Enrollment Status Page.

The existing tenant configuration was preserved without unnecessary changes to the default Enrollment Status Page or creation of duplicate Autopilot profiles.
