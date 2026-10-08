# LAB-03 — Conditional Access: Require Compliant Device

## Objective

Configure a Microsoft Entra Conditional Access policy that evaluates whether users are accessing organizational resources from a device that is marked as compliant by Microsoft Intune.

The policy is configured in **Report-only** mode so its impact can be evaluated without immediately enforcing access restrictions.

---

## Lab Scenario

The organization wants to strengthen access control by requiring users to access organizational resources from compliant devices.

Microsoft Intune provides the device compliance state, while Microsoft Entra Conditional Access uses that state when evaluating access.

For this lab, the policy is intentionally not enforced. This allows the administrator to test and evaluate the configuration before moving to an enforced deployment.

---

## Environment

| Component               | Configuration      |
| ----------------------- | ------------------ |
| Identity platform       | Microsoft Entra ID |
| Management platform     | Microsoft Intune   |
| Test user/group         | MD102-Pilot-Users  |
| Device platform         | Windows 11         |
| Conditional Access mode | Report-only        |
| Compliance source       | Microsoft Intune   |

---

## Conditional Access Policy

### Policy Name

`LAB-03-CA-Require-Compliant-Device`

### Policy Mode

**Report-only**

### Target Resources

**All resources**

### Included Users/Groups

`MD102-Pilot-Users`

### Grant Control

**Require device to be marked as compliant**

### Device Conditions

The policy configuration included the configured device exclusion for:

**Any device with 4 excluded**

### Client Apps

**1 client app included**

---

## Access Flow

The configuration establishes the following relationship:

```text
User
 |
 v
Microsoft Entra ID
 |
 v
Conditional Access
 |
 | Is the device compliant?
 v
Microsoft Intune compliance state
 |
 +---- Compliant ------> Access can satisfy the policy
 |
 +---- Noncompliant ---> Access requirement is not satisfied
```

This demonstrates how identity and endpoint management controls can work together.

---

## Why Report-only Mode Was Used

The policy targets **All resources**, which can include important administrative and organizational resources.

Enforcing the policy immediately could potentially prevent access for users or administrators whose devices do not yet satisfy the compliance requirement.

For this reason, the policy was deliberately configured as:

**Report-only**

This allows the administrator to evaluate the policy before enabling enforcement.

---

## Testing and Verification

The Conditional Access policy was created successfully and targeted at the MD-102 pilot group.

The policy was not switched to **On** mode during the lab.

The primary objective was to verify that Microsoft Entra Conditional Access could be configured to use the Intune compliance state as an access requirement.

This lab therefore focused on policy configuration and safe testing rather than intentionally blocking access.

---

## Troubleshooting

A warning was displayed because the Conditional Access policy targeted **All resources**, including the Azure portal.

This highlighted an important administrative consideration: broad Conditional Access policies must be introduced carefully because they can affect administrative access as well as normal user access.

Using **Report-only** mode avoided introducing an immediate access lockout while the configuration was being tested.

---

## Key Administration Concepts

### Conditional Access

Conditional Access provides policy-based access control in Microsoft Entra ID.

Access decisions can be based on conditions such as:

* User or group
* Target resources
* Device state
* Client application
* Location
* Risk
* Authentication requirements

### Device Compliance

Intune evaluates whether a managed device satisfies the organization's compliance requirements.

Conditional Access can then use that compliance state when making an access decision.

### Report-only Deployment

Report-only mode is useful when introducing a new Conditional Access policy.

It allows administrators to assess the policy's potential impact before enforcing it.

---

## Security Considerations

Conditional Access policies should be introduced carefully, particularly when they target broad resources.

Administrators should consider:

* Emergency or break-glass accounts
* Administrative access
* Pilot groups
* Device compliance state
* Exclusions
* Sign-in impact
* Report-only testing before enforcement

A staged deployment reduces the risk of unintentionally locking users or administrators out of required resources.

---

## Lessons Learned

This lab demonstrated that endpoint compliance and identity access control are closely connected.

A device can be managed by Intune, but Conditional Access can use the device's compliance state as an additional security signal.

The lab also demonstrated why **Report-only** mode is valuable when testing broad Conditional Access policies.

---

## Outcome

The `LAB-03-CA-Require-Compliant-Device` Conditional Access policy was successfully created.

The policy:

* Targets the MD-102 pilot group.
* Applies to all resources.
* Requires the device to be marked as compliant.
* Is configured in Report-only mode.
* Includes the configured device exclusion.
* Includes one client app.

The policy was deliberately not enforced during the lab.

---

## Skills Demonstrated

* Microsoft Entra Conditional Access
* Microsoft Intune compliance integration
* Report-only Conditional Access deployment
* Group-based access policy targeting
* Device compliance-based access control
* Conditional Access troubleshooting
* Safe policy deployment practices
* Endpoint and identity security integration

---

## Lab Status

**Completed**

Policy:

`LAB-03-CA-Require-Compliant-Device`

Mode:

**Report-only**

Assignment:

`MD102-Pilot-Users`

Grant control:

**Require device to be marked as compliant**
