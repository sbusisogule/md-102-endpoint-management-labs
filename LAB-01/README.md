# LAB-01 — Windows 11 Standard Configuration

## Objective

Configure a baseline Windows 11 security and account configuration using Microsoft Intune Settings Catalog.

The goal of this lab is to demonstrate how an endpoint administrator can centrally configure Windows security settings and apply them to a controlled pilot group.

---

## Lab Scenario

The organization wants to establish a standard Windows 11 configuration for pilot devices.

The configuration should enforce:

* A minimum password length of 12 characters.
* A maximum password age of 90 days.
* Centralized management through Microsoft Intune.
* Deployment to the `MD102-Pilot-Users` pilot group.

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
| Configuration type  | Settings Catalog      |

---

## Configuration

### Policy Name

`LAB-01-WIN11-Standard-Configuration`

### Policy Type

**Windows 10 and later — Settings catalog**

### Assignment

**Included group:**

`MD102-Pilot-Users`

### Configured Settings

The following password settings were configured under **Device Lock**:

| Setting                 | Configuration |
| ----------------------- | ------------- |
| Minimum Password Length | 12 characters |
| Maximum Password Age    | 90 days       |

---

## Deployment Process

The configuration was created in Microsoft Intune using the Settings Catalog.

The policy was then assigned to the `MD102-Pilot-Users` security group.

The test environment consisted of a Microsoft Entra joined Windows 11 Enterprise virtual machine managed by Microsoft Intune.

---

## Validation

The policy assignment was targeted at the `MD102-Pilot-Users` group.

Intune reporting was observed during the deployment process.

Because Intune policy processing and reporting can take time to synchronize, the lab focused on validating the policy configuration and assignment rather than waiting indefinitely for reporting status to change.

The policy was therefore considered successfully configured and deployed from the Intune administration perspective.

---

## Key Administration Concepts

This lab demonstrates several important Microsoft Intune administration concepts:

### Settings Catalog

The Settings Catalog provides administrators with a centralized collection of configurable Windows settings.

Instead of manually configuring every endpoint, administrators can define a configuration once and deploy it to targeted users or devices.

### Group-Based Assignment

The policy was assigned to:

`MD102-Pilot-Users`

Using a pilot group allows administrators to test configuration changes on a controlled population before broader deployment.

### Password Policy Management

Centralizing password requirements through Intune helps organizations maintain consistent endpoint security standards.

The lab configured:

* Minimum password length
* Maximum password age

---

## Troubleshooting / Lessons Learned

Intune policy deployment and reporting are not always immediate.

During this lab, Intune reporting initially showed limited or delayed status information.

This demonstrated an important real-world administration lesson:

> A policy being configured correctly does not always mean that the endpoint reporting interface will immediately show the final deployment state.

For this reason, administrators should distinguish between:

1. Policy configuration
2. Policy assignment
3. Policy processing
4. Endpoint configuration
5. Reporting synchronization

These stages may occur at different times.

---

## Outcome

The `LAB-01-WIN11-Standard-Configuration` policy was successfully created and assigned to the MD-102 pilot environment.

The lab established a baseline Windows 11 password configuration using Microsoft Intune Settings Catalog.

---

## Skills Demonstrated

* Microsoft Intune administration
* Windows 11 endpoint management
* Settings Catalog configuration
* Password policy management
* Microsoft Entra ID group-based targeting
* Intune policy assignment
* Endpoint configuration troubleshooting
* Understanding Intune policy processing and reporting

---

## Lab Status

**Completed**

Policy:

`LAB-01-WIN11-Standard-Configuration`

Assignment:

`MD102-Pilot-Users`
