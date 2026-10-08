# LAB-14 — Endpoint Security Baseline

## Objective

Document and evaluate an endpoint-security baseline approach through Microsoft Intune for managed Windows 11 devices.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`

## Configuration

LAB-14 focused on the design and administration of a layered Windows endpoint-security baseline.

The lab brought together security controls implemented across the MD-102 lab sequence, including:

* Microsoft Defender Antivirus
* Windows Firewall
* Windows LAPS
* BitLocker
* Windows Hello for Business
* Compliance policies
* Conditional Access

These controls demonstrate how multiple security mechanisms can contribute to an overall enterprise endpoint-security strategy.

**LAB-14 does not claim that all of these controls were configured by a single Intune policy or profile.** Individual controls were implemented and documented in their respective labs.

## Policy Management

The endpoint-security configuration was reviewed through the Microsoft Intune admin center.

The `MD102-Pilot-Users` group was used throughout the lab environment as the controlled pilot scope for endpoint-management testing.

Pilot deployment provides a controlled way to evaluate security configurations before considering broader deployment.

## Security Principles Demonstrated

### Defense in Depth

Multiple security controls work together rather than relying on a single security mechanism.

### Least Privilege

Administrative access and endpoint permissions should be restricted to what is required.

### Pilot Deployment

Security configurations should initially be evaluated against a controlled group before wider deployment.

### Centralized Management

Microsoft Intune provides a central management plane for configuring and monitoring managed Windows endpoints.

## Validation

The security configuration and related policies were reviewed in Microsoft Intune.

Because Intune policy processing and reporting can be asynchronous, this lab documents the configuration and security-baseline approach rather than claiming successful endpoint application of every individual control.

Endpoint-level validation for specific controls is documented in their respective labs where evidence was available.

## Skills Demonstrated

* Microsoft Intune endpoint-security management
* Security policy administration
* Windows 11 security controls
* Pilot-group deployment
* Defense-in-depth principles
* Enterprise endpoint administration
* Policy scope management
* Configuration validation
* Security-policy troubleshooting

## Outcome

LAB-14 demonstrated how individual endpoint-security controls can be considered as components of a broader Windows security baseline.

The lab reinforced the importance of defense in depth, controlled pilot deployment, centralized management, and evidence-based validation when managing enterprise endpoints.

## Evidence Status

**Status: Configured / Security Baseline Documented**

LAB-14 documents the endpoint-security baseline approach. Individual security-control implementation and validation are documented separately in the relevant labs.
