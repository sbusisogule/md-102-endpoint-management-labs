# LAB-16 — Windows Update Management

## Objective

Configure Windows Update management through Microsoft Intune to control how Windows 11 devices receive quality and feature updates.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-16 focused on centralized Windows Update management through Microsoft Intune.

The lab demonstrated how an administrator can manage Windows Update behaviour for organizational devices rather than relying entirely on local Windows Update settings.

The configuration was evaluated as part of the broader Windows endpoint-management environment.

## Management Concepts

The lab covered the administrative concepts associated with:

* Windows quality updates
* Windows feature updates
* Update deferrals
* Update deployment control
* Restart behaviour
* Active hours
* Pilot deployment
* Update compliance

## Pilot Deployment

The `MD102-Pilot-Users` group was used as the pilot scope.

A pilot deployment allows administrators to evaluate Windows Update policies on a controlled population before expanding the configuration to additional users and devices.

## Validation

The Windows Update configuration was reviewed through Microsoft Intune.

The Windows 11 test device was already running Windows 11 25H2, so the lab did not require forcing a feature upgrade on the VM.

Where Intune reporting or Windows Update UI information was delayed or unavailable, the configured policy was documented rather than waiting indefinitely for asynchronous reporting.

## Administrative Considerations

Windows Update policies should be designed carefully because multiple policies can target the same device.

Conflicting update settings can result in policy conflicts or unexpected behaviour.

A practical enterprise approach is therefore:

1. Define the update-management strategy.
2. Create a controlled pilot.
3. Test quality and feature update behaviour.
4. Monitor compliance.
5. Resolve conflicts.
6. Expand the deployment gradually.

## Skills Demonstrated

* Microsoft Intune Windows Update management
* Windows 11 update administration
* Quality and feature update concepts
* Update policy deployment
* Pilot-group management
* Policy conflict awareness
* Endpoint update troubleshooting

## Outcome

LAB-16 demonstrated the fundamentals of centrally managing Windows 11 updates through Microsoft Intune.

The lab reinforced the importance of controlled update deployment, pilot testing, policy consistency, and endpoint validation.
