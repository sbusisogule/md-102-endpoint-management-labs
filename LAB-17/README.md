# LAB-17 — Windows Update Compliance

## Objective

Configure and evaluate Windows Update compliance requirements for managed Windows 11 devices using Microsoft Intune.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-17 focused on the relationship between Windows Update management and device compliance.

The lab demonstrated how administrators can establish operating-system requirements and use Microsoft Intune compliance policies to identify devices that do not meet the organization's required Windows baseline.

## Compliance Approach

The compliance configuration considered:

* Minimum supported Windows version
* Windows security requirements
* Device compliance state
* Noncompliance actions
* Pilot-group deployment

The `MD102-Pilot-Users` group was used as the controlled deployment scope.

## Validation

The compliance policy was reviewed in Microsoft Intune.

The Windows 11 test device was already running Windows 11 25H2, providing an appropriate operating-system baseline for the lab.

Intune compliance reporting was allowed to remain asynchronous where necessary rather than delaying the lab for reporting changes.

## Conditional Access Relationship

Device compliance can be used as a condition for Microsoft Entra Conditional Access.

The broader MD-102 environment included a Conditional Access policy configured in **Report-only** mode that required a device to be marked as compliant.

This allowed the compliance workflow to be evaluated without immediately enforcing access restrictions.

## Administrative Workflow

A practical endpoint-management workflow is:

1. Define the supported Windows baseline.
2. Create the compliance requirement.
3. Assign it to a pilot group.
4. Monitor device compliance.
5. Investigate noncompliant devices.
6. Remediate issues.
7. Use Conditional Access to enforce compliance when appropriate.

## Skills Demonstrated

* Microsoft Intune compliance policies
* Windows 11 compliance requirements
* Operating-system version management
* Device compliance monitoring
* Conditional Access concepts
* Pilot deployment
* Endpoint compliance troubleshooting

## Outcome

LAB-17 demonstrated how Windows operating-system requirements can be incorporated into an Intune compliance strategy.

The lab reinforced the relationship between device configuration, compliance evaluation, and Conditional Access enforcement.
