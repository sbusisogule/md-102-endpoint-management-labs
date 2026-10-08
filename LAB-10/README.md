# LAB-10 — Windows Endpoint Security Policy

## Objective

Configure and evaluate an additional Windows endpoint security policy through Microsoft Intune as part of the MD-102 pilot environment.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-10 was created as part of the Windows endpoint-management policy set used throughout the MD-102 lab environment.

The policy was initially assigned to the `MD102-Pilot-Users` group for testing and evaluation.

During the lab sequence, a policy overlap/conflict was identified with the later Windows Update Ring configuration in LAB-20.

To avoid maintaining competing configurations, the LAB-10 assignment was subsequently removed.

## Policy Management

The lab demonstrated an important Intune administration principle:

> Multiple policies can target the same device, and overlapping settings can result in conflicts or unexpected configuration behaviour.

Rather than leaving potentially conflicting assignments in place, the LAB-10 assignment was removed so that the later update-management configuration could be evaluated independently.

## Assignment

| Item                | Configuration        |
| ------------------- | -------------------- |
| Original Assignment | `MD102-Pilot-Users`  |
| Final Assignment    | Removed              |
| Test Device         | `INTUNE-USER`        |
| Platform            | Windows 10 and later |

## Validation

The policy configuration was reviewed in Microsoft Intune.

The assignment was subsequently removed as part of policy conflict management.

This was intentional and was not treated as a failed lab.

## Skills Demonstrated

* Microsoft Intune policy creation
* Policy assignments
* Pilot-group management
* Identifying policy overlap
* Managing Intune configuration conflicts
* Understanding the importance of policy scope
* Maintaining a clean endpoint-management baseline

## Outcome

LAB-10 demonstrated the administrative process of creating, assigning, reviewing, and managing an Intune policy while considering interactions with other endpoint-management policies.

The assignment was intentionally removed later in the lab sequence to prevent configuration conflicts with LAB-20.

This reflects a realistic endpoint-management workflow in which administrators must manage policy interactions rather than simply create policies in isolation.
