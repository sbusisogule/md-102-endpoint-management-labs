# LAB-14 — Endpoint Security Baseline

## Objective

Configure and evaluate an endpoint security baseline through Microsoft Intune to strengthen the security posture of managed Windows 11 devices.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-14 focused on applying endpoint security controls through Microsoft Intune.

The lab builds on the security controls configured in earlier labs, including:

* Microsoft Defender Antivirus
* Windows Firewall
* Windows LAPS
* BitLocker
* Windows Hello for Business
* Compliance policies
* Conditional Access

The goal was to demonstrate how these controls can form part of a broader enterprise endpoint-security strategy.

## Policy Management

The endpoint security configuration was reviewed and managed from the Microsoft Intune admin center.

The `MD102-Pilot-Users` group was used as the pilot scope for endpoint-management testing.

Using a pilot group allows administrators to validate security settings on a controlled set of users and devices before broader deployment.

## Validation

The policy configuration was reviewed in Microsoft Intune.

Because Intune reporting and policy processing can be asynchronous, endpoint reporting was not treated as the sole measure of completion. The configuration itself was validated and documented as part of the lab.

## Security Principles Demonstrated

### Defense in Depth

Multiple security controls are used together rather than relying on a single protection mechanism.

### Least Privilege

Administrative access and endpoint permissions should be restricted to what is required.

### Pilot Deployment

Security policies should initially be tested against a controlled group before organization-wide deployment.

### Centralized Management

Microsoft Intune provides a central management plane for applying and monitoring Windows security configurations.

## Skills Demonstrated

* Microsoft Intune endpoint security
* Security policy management
* Windows 11 security controls
* Pilot-group deployment
* Defense-in-depth principles
* Enterprise endpoint administration
* Policy validation and troubleshooting

## Outcome

LAB-14 demonstrated how Microsoft Intune can be used to build and manage a layered Windows endpoint-security baseline.

The lab reinforced the importance of combining multiple security controls and validating changes through a controlled pilot environment before wider deployment.
