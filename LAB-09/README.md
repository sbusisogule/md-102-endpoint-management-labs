# LAB-09 — Windows Firewall: Allow RDP

## Objective

Create an explicit Windows Firewall inbound rule through Microsoft Intune to allow Remote Desktop Protocol (RDP) traffic on Windows 11 pilot devices.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

A Windows Firewall rule was configured in Microsoft Intune and assigned to the `MD102-Pilot-Users` group.

The rule was designed to permit inbound Remote Desktop traffic while the Windows Firewall baseline from LAB-08 continues to block unsolicited inbound connections by default.

## Firewall Rule

| Setting         | Configuration       |
| --------------- | ------------------- |
| Rule Name       | `Allow-RDP-Inbound` |
| Direction       | Inbound             |
| Action          | Allow               |
| Enabled         | Yes                 |
| Interfaces      | All                 |
| Protocol        | TCP                 |
| Protocol Number | `6`                 |
| Local Port      | `3389`              |
| Remote Ports    | `0-65535`           |
| Assignment      | `MD102-Pilot-Users` |

## Security Context

LAB-08 established a default inbound firewall action of **Block**.

LAB-09 demonstrates how an administrator can create a specific exception for a required service without changing the overall secure-by-default firewall posture.

Remote Desktop uses TCP port `3389`, so the firewall rule explicitly permits inbound TCP traffic to that local port.

## Validation

The firewall rule was configured successfully in Microsoft Intune.

The Windows 11 test VM was also checked using the Windows Firewall management interface, where the firewall was confirmed to be enabled.

Intune policy reporting may take time to reflect endpoint-level application, so validation was focused on the policy configuration and endpoint firewall state rather than waiting for reporting to settle.

## Skills Demonstrated

* Microsoft Intune firewall rule management
* Windows Firewall inbound rules
* TCP/IP fundamentals
* RDP port configuration
* Secure-by-default firewall design
* Intune policy assignments
* Endpoint security validation

## Outcome

LAB-09 demonstrated how to create a controlled Windows Firewall exception for Remote Desktop while maintaining the broader firewall security baseline established in LAB-08.

This represents a common endpoint-management scenario where a specific business or administrative service must be permitted through an otherwise restrictive firewall policy.
