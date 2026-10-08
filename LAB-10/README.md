# LAB-10 — Intune Policy Assignment and Conflict Management

## Objective

Create, assign, review, and manage an additional Windows endpoint-management policy in Microsoft Intune while evaluating its interaction with other policies in the MD-102 pilot environment.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-10 was created as part of the Windows endpoint-management policy exercises in the MD-102 lab environment.

The policy was initially assigned to the `MD102-Pilot-Users` group for testing and evaluation.

During the wider lab sequence, an overlap/conflict was identified involving the later Windows Update Ring configuration in LAB-20.

To avoid maintaining competing assignments, the LAB-10 assignment was subsequently removed.

## Policy Management

This lab demonstrated an important Microsoft Intune administration principle:

> Multiple policies can target the same device, and overlapping configuration settings can result in conflicts or unexpected behaviour.

Rather than leaving a potentially conflicting assignment in place, the LAB-10 assignment was removed so that the later update-management configuration could be evaluated independently.

This represents normal administrative policy hygiene rather than a failed configuration.

## Assignment

| Item                | Configuration        |
| ------------------- | -------------------- |
| Original Assignment | `MD102-Pilot-Users`  |
| Final Assignment    | Removed              |
| Test Device         | `INTUNE-USER`        |
| Platform            | Windows 10 and later |

## Validation

The policy configuration and assignment were reviewed in Microsoft Intune.

The assignment was subsequently removed as part of managing policy overlap with the later LAB-20 configuration.

Endpoint-level successful application of the LAB-10 policy is **not claimed** because the assignment was removed before a definitive endpoint result was established.

## Skills Demonstrated

* Microsoft Intune policy creation
* Policy assignment management
* Pilot-group management
* Identifying policy overlap
* Managing configuration conflicts
* Understanding policy scope
* Maintaining a clean endpoint-management baseline
* Evaluating policy interactions

## Outcome

LAB-10 demonstrated the administrative process of creating and assigning an Intune policy, reviewing its interaction with the wider policy environment, and deliberately removing an assignment when policy overlap was identified.

The assignment was removed later in the lab sequence to prevent configuration conflicts with LAB-20.

This reflects a realistic endpoint-management workflow in which administrators must consider policy interactions and assignment scope rather than managing policies in isolation.

## Evidence Status

**Status: Configured / Assignment Removed**

No endpoint-level successful application of the LAB-10 policy is claimed.
