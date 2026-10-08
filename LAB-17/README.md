# LAB-17 — Windows Update Compliance

## Objective

Document and evaluate how Windows Update requirements can be incorporated into a Microsoft Intune device-compliance strategy for managed Windows 11 devices.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-17 focused on the relationship between Windows Update management and device compliance.

The lab examined how administrators can establish supported Windows operating-system requirements and use Microsoft Intune compliance policies to evaluate whether managed devices meet the organization's baseline.

Specific compliance-policy configuration and validation were subsequently demonstrated in other labs, including LAB-22.

## Compliance Approach

The compliance workflow considered:

* Minimum supported Windows version
* Windows security requirements
* Device compliance state
* Noncompliance actions
* Pilot-group deployment

The `MD102-Pilot-Users` group was used throughout the lab environment as the controlled pilot scope.

## Validation

The compliance workflow was reviewed through Microsoft Intune.

The Windows 11 test device was already running Windows 11 Enterprise 25H2, providing an appropriate operating-system baseline for the lab environment.

Intune compliance reporting can be asynchronous. The lab therefore documents the compliance-management workflow rather than claiming a specific endpoint compliance result that was not independently validated for LAB-17.

## Conditional Access Relationship

Device compliance can be used as a condition for Microsoft Entra Conditional Access.

The broader MD-102 environment included a Conditional Access policy configured in **Report-only** mode requiring devices to be marked as compliant.

This allowed the relationship between compliance evaluation and Conditional Access to be demonstrated without immediately enforcing access restrictions.

## Administrative Workflow

A practical endpoint-management workflow is:

1. Define the supported Windows baseline.
2. Create the compliance requirement.
3. Assign it to a pilot group.
4. Monitor device compliance.
5. Investigate noncompliant devices.
6. Remediate identified issues.
7. Use Conditional Access to enforce compliance when appropriate.

## Skills Demonstrated

* Microsoft Intune compliance management
* Windows 11 compliance requirements
* Operating-system version management
* Device compliance concepts
* Conditional Access concepts
* Pilot deployment
* Endpoint compliance troubleshooting
* Compliance-policy planning

## Outcome

LAB-17 demonstrated the relationship between Windows Update requirements, Intune compliance evaluation, and Conditional Access.

The lab reinforced that update management and compliance management are related but distinct administrative functions.

Concrete compliance-policy configuration and endpoint validation are documented in the relevant labs elsewhere in this portfolio.

## Evidence Status

**Status: Configured / Compliance Workflow Documented**

LAB-17 documents the Windows Update compliance workflow. Specific compliance-policy settings and endpoint results are documented separately where independently validated.
