# LAB-16 — Windows Update Management

## Objective

Document and evaluate Windows Update management through Microsoft Intune as part of the Windows 11 endpoint-management strategy.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-16 focused on the administrative concepts involved in centrally managing Windows Update through Microsoft Intune.

The lab examined how organizations can use Intune to manage Windows update behaviour rather than relying entirely on local device configuration.

Specific Windows Update Ring configuration and deployment settings were implemented separately in LAB-20.

## Management Concepts

The lab covered the administration and planning considerations associated with:

* Windows quality updates
* Windows feature updates
* Update deferrals
* Update deployment control
* Restart behaviour
* Active hours
* Pilot deployment
* Update compliance

These concepts form part of a broader Windows update-management strategy.

## Pilot Deployment

The `MD102-Pilot-Users` group was used throughout the lab environment as the controlled pilot scope.

A pilot deployment allows administrators to evaluate update-management configurations on a limited population before expanding deployment.

## Validation

The Windows Update management approach was reviewed through Microsoft Intune.

The Windows 11 test device was already running Windows 11 25H2, so no feature upgrade was required for the lab environment.

Where Intune reporting or Windows Update UI information was delayed or unavailable, the documented configuration and management approach were used rather than waiting indefinitely for asynchronous reporting.

The lab does not claim that every Windows Update management setting listed above was independently validated at the endpoint.

## Administrative Considerations

Windows Update policies must be designed carefully because multiple policies can target the same device.

Overlapping update settings can result in policy conflicts or unexpected behaviour.

A practical enterprise approach is therefore:

1. Define the update-management strategy.
2. Create a controlled pilot.
3. Test update behaviour.
4. Monitor compliance and reporting.
5. Resolve policy conflicts.
6. Expand deployment gradually.

## Skills Demonstrated

* Microsoft Intune Windows Update management
* Windows 11 update administration
* Quality and feature update concepts
* Update policy planning
* Pilot-group management
* Policy conflict awareness
* Endpoint update troubleshooting

## Outcome

LAB-16 demonstrated the fundamentals and administrative considerations of centrally managing Windows 11 updates through Microsoft Intune.

The lab reinforced the importance of controlled deployment, pilot testing, policy consistency, and evidence-based endpoint validation.

Specific Update Ring configuration was subsequently demonstrated in LAB-20.

## Evidence Status

**Status: Configured / Management Concepts Documented**

LAB-16 documents the Windows Update management approach. Specific Update Ring settings and assignment behaviour are documented separately in LAB-20.
