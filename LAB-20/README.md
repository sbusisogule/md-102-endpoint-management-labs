# LAB-20 — Windows Update Ring

## Objective

Create a Microsoft Intune Update Ring policy to control Windows 11 quality updates, feature updates, restart behaviour, and update-management settings.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Update Ring Configuration

The following Windows Update Ring settings were configured:

| Setting                                         | Configuration                |
| ----------------------------------------------- | ---------------------------- |
| Microsoft product updates                       | Allow                        |
| Windows drivers                                 | Allow                        |
| Quality update deferral                         | 7 days                       |
| Feature update deferral                         | 14 days                      |
| Upgrade Windows 10 devices to latest Windows 11 | No                           |
| Feature update uninstall period                 | 10 days                      |
| Pre-release builds                              | General Availability channel |
| Automatic install/restart                       | Automatic during maintenance |
| Active hours                                    | 08:00–17:00                  |
| Pause updates                                   | Enable                       |
| Check for updates                               | Enable                       |
| Update notifications                            | Default                      |
| Deadline settings                               | Not configured               |

## Assignment

The Update Ring was assigned to:

```text
MD102-Pilot-Users
```

The policy initially showed a configuration conflict during the lab sequence.

Because multiple update-management policies existed in the lab environment, policy overlap was considered as a possible cause.

## Policy Management

LAB-20 was kept separate from other Windows Update configurations to reduce the possibility of conflicting settings.

The earlier LAB-10 assignment was removed during the lab sequence to avoid overlap with the later Update Ring configuration.

## Endpoint Validation

The Windows 11 test VM was already running:

```text
Windows 11 Enterprise 25H2
OS Build 26200.6584
```

Therefore, no feature upgrade was required during this lab.

During later integrated validation, `LAB-20-WIN11-Update-Ring` was not visible in the device's assigned-policy list.

The lab therefore does **not** claim that the Update Ring was successfully applied to the endpoint.

The documented outcome is that the policy was created and configured, while endpoint-level assignment/application remained unconfirmed.

## Administrative Lesson

Windows Update management requires careful policy design because multiple policies can target the same devices.

Administrators should:

1. Establish a single intended update strategy.
2. Use pilot groups.
3. Avoid overlapping update policies.
4. Monitor conflicts.
5. Validate the effective device configuration.
6. Expand deployment after successful testing.

## Skills Demonstrated

* Microsoft Intune Update Rings
* Windows Update for Business concepts
* Quality update deferrals
* Feature update deferrals
* Restart and maintenance settings
* Active hours
* Update policy assignments
* Policy conflict troubleshooting
* Endpoint update validation

## Outcome

LAB-20 demonstrated how to create and configure a Windows Update Ring for managed Windows 11 devices.

The policy configuration was completed and assigned to the pilot group. However, endpoint-level application was not confirmed during the final validation, so the portfolio deliberately does not claim successful deployment.

This distinction reflects real-world Intune administration, where policy creation, assignment, processing, and effective endpoint configuration are separate validation stages.
