# LAB-07 — Windows 11 Microsoft Defender Antivirus

## Objective

Configure Microsoft Defender Antivirus settings through Microsoft Intune to establish a baseline endpoint protection policy for Windows 11 devices.

The purpose of this lab is to demonstrate centralized antivirus configuration, pilot-group deployment, and endpoint security management using Microsoft Intune.

---

## Lab Scenario

The organization wants to establish a baseline Microsoft Defender Antivirus configuration for Windows 11 pilot devices.

The policy should enable core antivirus and endpoint protection capabilities, including:

* Real-time monitoring
* Cloud protection
* Behavior monitoring
* Script scanning
* Email scanning
* Archive scanning
* Scanning of downloaded files and attachments
* Full-scan protection for mapped and removable drives

The configuration is deployed to the MD-102 pilot group.

---

## Environment

| Component           | Configuration         |
| ------------------- | --------------------- |
| Management platform | Microsoft Intune      |
| Identity platform   | Microsoft Entra ID    |
| Operating system    | Windows 11 Enterprise |
| Windows version     | 25H2                  |
| OS build            | 26200.6584            |
| Test device         | INTUNE-USER           |
| Test user           | MD102 Test User       |
| Assignment group    | MD102-Pilot-Users     |

---

## Defender Antivirus Policy

### Policy Name

`LAB-07-WIN11-Defender-Antivirus`

### Platform

**Windows 10 and later**

### Assignment

`MD102-Pilot-Users`

The policy was configured as an endpoint security antivirus policy and assigned to the pilot group.

---

## Configured Protection Settings

The policy included the following Defender Antivirus protections:

| Protection Setting               | Configuration |
| -------------------------------- | ------------- |
| Archive scanning                 | Configured    |
| Behavior monitoring              | Configured    |
| Cloud protection                 | Configured    |
| Email scanning                   | Configured    |
| Full scan — mapped drives        | Configured    |
| Full scan — removable drives     | Configured    |
| Real-time monitoring             | Configured    |
| Script scanning                  | Configured    |
| Downloaded files and attachments | Configured    |

These settings provide multiple layers of malware and threat detection.

---

## Protection Architecture

The endpoint protection model can be represented as:

```text id="7y5d1m"
Windows 11 Device
       |
       v
Microsoft Intune
       |
       v
Defender Antivirus Policy
       |
       +-- Real-time Monitoring
       +-- Cloud Protection
       +-- Behavior Monitoring
       +-- Script Scanning
       +-- Email Scanning
       +-- Archive Scanning
       +-- Download Scanning
       +-- Drive Scanning
       |
       v
Microsoft Defender Antivirus
       |
       v
Endpoint Protection
```

---

## Deployment

The Defender Antivirus policy was assigned to:

`MD102-Pilot-Users`

The policy was intended to provide a centrally managed antivirus baseline for the Windows 11 pilot environment.

During deployment, Intune initially displayed the policy status as **Pending**.

The lab did not wait indefinitely for the Intune reporting state to change.

---

## Validation

The policy configuration and assignment were verified in Microsoft Intune.

The endpoint was already:

* Microsoft Entra joined
* Intune managed
* Assigned to the MD-102 pilot environment

The policy was therefore considered configured and assigned successfully from the Intune administration perspective.

The initial **Pending** status was documented as part of the deployment behavior rather than treated as evidence that the policy configuration itself was incorrect.

---

## Troubleshooting / Lessons Learned

A key lesson from this lab was the difference between policy configuration and policy processing.

The administrator must distinguish between:

1. Creating the policy.
2. Assigning the policy.
3. Device check-in.
4. Policy processing.
5. Endpoint configuration.
6. Reporting synchronization.

Intune can continue to show **Pending** while the endpoint management service processes the assignment.

This is particularly important in a lab environment where repeatedly waiting for portal reporting can significantly slow down the learning process.

---

## Security Considerations

Microsoft Defender Antivirus should be considered one component of a broader endpoint security strategy.

Antivirus protection works alongside other controls such as:

* Windows Firewall
* BitLocker
* Windows LAPS
* Windows Update
* Microsoft Intune compliance
* Microsoft Entra Conditional Access
* Endpoint remediation

A layered security architecture provides stronger protection than relying on a single security control.

---

## Defender for Endpoint Consideration

The lab environment also included investigation of the Microsoft Defender for Endpoint connector.

At the time of validation, the connector was not available for endpoint onboarding and showed an unavailable/stopped state.

No Windows devices were shown as onboarded to Defender for Endpoint.

This was documented separately from the Microsoft Defender Antivirus configuration.

The absence of Defender for Endpoint onboarding did not prevent the Defender Antivirus policy from being configured through Intune.

---

## Key Administration Concepts

### Microsoft Defender Antivirus

Microsoft Defender Antivirus provides built-in malware and threat protection for Windows devices.

### Endpoint Security Policies

Intune endpoint security policies provide purpose-built configuration areas for security controls such as antivirus, firewall, and disk encryption.

### Cloud Protection

Cloud-based protection can provide additional threat intelligence when evaluating suspicious files and activity.

### Real-time Protection

Real-time monitoring provides continuous protection while users interact with files, applications, and system activity.

### Pilot Deployment

Assigning the policy to `MD102-Pilot-Users` allows the administrator to validate the configuration before expanding it to a larger population.

---

## Outcome

The `LAB-07-WIN11-Defender-Antivirus` policy was successfully created and assigned to the MD-102 pilot group.

The policy included multiple Defender Antivirus protection settings covering:

* Real-time protection
* Cloud protection
* Behavior monitoring
* Script scanning
* Email scanning
* Archive scanning
* Downloaded files and attachments
* Mapped drives
* Removable drives

The initial Intune deployment status was **Pending**, and the lab proceeded without waiting indefinitely for portal reporting to complete.

---

## Skills Demonstrated

* Microsoft Intune endpoint security
* Microsoft Defender Antivirus
* Antivirus policy configuration
* Windows 11 security management
* Endpoint security baseline design
* Group-based policy assignment
* Intune deployment troubleshooting
* Microsoft Defender for Endpoint concepts
* Layered endpoint security

---

## Lab Status

**Completed**

Policy:

`LAB-07-WIN11-Defender-Antivirus`

Assignment:

`MD102-Pilot-Users`

Deployment status observed:

**Pending during initial processing**
