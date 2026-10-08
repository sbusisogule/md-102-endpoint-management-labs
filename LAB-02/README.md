# LAB-02 — Windows 11 Basic Compliance

## Objective

Create a Microsoft Intune compliance policy for Windows 11 and configure a Conditional Access policy that can use device compliance as an access control signal.

The purpose of this lab is to demonstrate how endpoint compliance and identity-based access controls work together in a Microsoft Entra ID and Microsoft Intune environment.

---

## Lab Scenario

The organization wants Windows 11 pilot devices to meet a basic security baseline before they are considered compliant.

The compliance requirements for the pilot environment are:

* Secure Boot must be enabled.
* Windows devices must meet the minimum operating system version.
* Devices that fail compliance should be marked noncompliant immediately.

A Conditional Access policy is also configured in **Report-only** mode to evaluate the requirement for devices to be marked compliant.

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

## Compliance Policy

### Policy Name

`LAB-02-WIN11-Basic-Compliance`

### Platform

**Windows 10 and later**

### Compliance Requirements

| Requirement          | Configuration                        |
| -------------------- | ------------------------------------ |
| Secure Boot          | Require                              |
| Minimum OS version   | 10.0.26100.0                         |
| Noncompliance action | Mark device noncompliant immediately |

The policy was assigned to:

`MD102-Pilot-Users`

---

## Conditional Access

A Microsoft Entra Conditional Access policy was also created to evaluate device compliance.

### Configuration

| Setting               | Configuration                            |
| --------------------- | ---------------------------------------- |
| Policy mode           | Report-only                              |
| Access control        | Require device to be marked as compliant |
| Target resources      | All resources                            |
| Included users/groups | Pilot group                              |
| Excluded identities   | 0                                        |
| Device exclusion      | Any device with 4 excluded               |
| Client apps           | 1 client app                             |

The policy was intentionally left in **Report-only** mode.

This allows an administrator to evaluate the effect of the policy without immediately blocking access for users who may not yet satisfy the compliance requirement.

---

## Validation

The Windows 11 test device was already Microsoft Entra joined and managed by Microsoft Intune.

The compliance policy was assigned to the pilot group.

During validation, Intune initially showed that the compliance policy was assigned but that Conditional Access was not yet being used to enforce compliance.

The compliance reporting later showed:

* Compliant: 0
* Noncompliant: 0
* Others: 0
* Total: 0

Because the environment was a controlled lab and Intune reporting can take time to synchronize, the lab was not extended indefinitely waiting for reporting changes.

The configuration and assignment were therefore documented as the primary outcome of the lab.

---

## Why Report-only Mode Was Used

Conditional Access policies can have a significant impact on user access.

Deploying a policy directly in **On** mode can potentially prevent users from accessing organizational resources.

Using **Report-only** mode allows administrators to:

1. Create the policy.
2. Evaluate what would happen.
3. Review sign-in results.
4. Identify unexpected exclusions or conditions.
5. Correct configuration problems.
6. Enable enforcement when ready.

This is a common approach when introducing Conditional Access policies in an enterprise environment.

---

## Key Administration Concepts

### Compliance Policies

Intune compliance policies evaluate whether managed devices meet defined organizational requirements.

Compliance can include requirements such as:

* Operating system versions
* Secure Boot
* Encryption
* Password requirements
* Defender security status
* Device threat levels

### Conditional Access

Microsoft Entra Conditional Access can use device compliance as part of an access decision.

This creates a relationship between endpoint management and identity security:

```text
Windows 11 Device
       |
       v
Microsoft Intune
       |
       | Compliance evaluation
       v
Compliant / Noncompliant
       |
       v
Microsoft Entra Conditional Access
       |
       v
Access decision
```

---

## Troubleshooting / Lessons Learned

One important lesson from this lab was that configuring a compliance policy and seeing a device as compliant are separate events.

An administrator needs to consider:

1. Policy configuration
2. Policy assignment
3. Device check-in
4. Compliance evaluation
5. Reporting synchronization
6. Conditional Access evaluation

These stages may not update simultaneously.

The lab also demonstrated why Conditional Access should be tested carefully before moving from **Report-only** to **On**.

---

## Security Considerations

The compliance policy establishes a basic security baseline, but it is not a complete enterprise security configuration.

Additional controls can be introduced through later labs, including:

* Windows LAPS
* Microsoft Defender Antivirus
* Windows Firewall
* BitLocker
* Windows Update management
* Endpoint remediation
* Application deployment

This lab therefore represents an early component of a broader endpoint security architecture.

---

## Outcome

The `LAB-02-WIN11-Basic-Compliance` compliance policy was successfully created and assigned to the MD-102 pilot group.

A Conditional Access policy requiring compliant devices was also created in Report-only mode.

The lab demonstrated the relationship between Microsoft Intune compliance and Microsoft Entra Conditional Access.

---

## Skills Demonstrated

* Microsoft Intune compliance policy configuration
* Windows 11 compliance management
* Secure Boot compliance
* Minimum OS version enforcement
* Microsoft Entra Conditional Access
* Report-only Conditional Access deployment
* Group-based policy assignment
* Compliance troubleshooting
* Endpoint security baseline design

---

## Lab Status

**Completed**

Compliance policy:

`LAB-02-WIN11-Basic-Compliance`

Assignment:

`MD102-Pilot-Users`

Conditional Access:

**Report-only — Require device to be marked as compliant**
