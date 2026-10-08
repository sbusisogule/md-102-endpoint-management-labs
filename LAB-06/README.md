# LAB-06 — Windows 11 Application Management: VLC

## Objective

Deploy a Windows application to managed Windows 11 devices using Microsoft Intune.

The purpose of this lab is to demonstrate application management, assignment targeting, installation behavior, and deployment monitoring in Microsoft Intune.

---

## Lab Scenario

The organization needs to deploy the VLC media player to a controlled group of Windows 11 pilot users.

The application should be centrally managed through Microsoft Intune and deployed as a required application to the pilot group.

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

## Application

### Application

**VLC media player**

### Publisher

**VideoLAN**

### Application Type

**Microsoft Store app (new)**

### Package

`XPDM1ZW6815MQM`

### Architecture

**Win32**

### Installation Context

**System**

---

## Assignment

The VLC application was configured as a **Required** application.

### Target Group

`MD102-Pilot-Users`

This means Intune was configured to automatically install the application on devices associated with the targeted pilot users.

---

## Deployment Configuration

The application was configured with:

* Required assignment
* Pilot-group targeting
* System installation
* Windows 11 device deployment
* Toast notification enabled
* Installation availability set to **ASAP**

The application was created in Intune as a Microsoft Store app using the new Microsoft Store application experience.

---

## Deployment Workflow

The application deployment process can be represented as:

```text
MD102-Pilot-Users
       |
       v
Microsoft Intune
       |
       v
VLC Application Assignment
       |
       v
Windows 11 Device
       |
       v
Application Installation
       |
       v
VLC Available on Device
```

---

## Validation

The VLC application was successfully configured and assigned to the MD-102 pilot group.

During the initial deployment, application installation took longer than expected.

Rather than waiting indefinitely for Intune application reporting to complete, the lab proceeded to the next endpoint-management exercise.

This demonstrated an important operational consideration: Intune application deployment and reporting may not be instantaneous after an assignment is created.

---

## Key Administration Concepts

### Microsoft Store Apps

Microsoft Intune can deploy applications from the Microsoft Store using the modern Microsoft Store app integration.

This reduces the need for administrators to manually package and maintain some applications.

### Required Applications

A **Required** assignment tells Intune that the application should be installed automatically on targeted devices.

This differs from an **Available** assignment, where the application is made available for users to install themselves.

### Group-Based Deployment

Targeting `MD102-Pilot-Users` allows the administrator to test the application deployment with a controlled population before expanding the deployment.

---

## Troubleshooting / Lessons Learned

The VLC deployment demonstrated that application assignment and application installation are separate stages.

The administrator should consider:

1. Application configuration
2. Assignment
3. Device check-in
4. Application evaluation
5. Installation
6. Detection
7. Reporting

A delay in the Intune portal does not necessarily mean the application configuration is incorrect.

The lab therefore focused on correctly configuring the application and its assignment rather than waiting indefinitely for installation reporting.

---

## Security and Administration Considerations

Application deployment should normally follow a controlled rollout process.

A common enterprise approach is:

```text
Pilot Group
     |
     v
Testing
     |
     v
Validation
     |
     v
Broader Deployment
```

Using a pilot group reduces the risk of deploying an application configuration incorrectly to the entire organization.

---

## Outcome

The VLC application was successfully created in Microsoft Intune as a Microsoft Store app (new).

The application was configured for:

* Win32 architecture
* System installation
* Required deployment
* `MD102-Pilot-Users` targeting
* ASAP installation
* Toast notifications

Application installation reporting was slower than expected, so the lab proceeded without waiting for the deployment to fully settle.

---

## Skills Demonstrated

* Microsoft Intune application management
* Microsoft Store application deployment
* Required application assignments
* Group-based application targeting
* Windows 11 application management
* Installation context configuration
* Application deployment troubleshooting
* Intune application monitoring
* Pilot-based application deployment

---

## Lab Status

**Completed**

Application:

**VLC media player**

Application type:

**Microsoft Store app (new)**

Assignment:

`MD102-Pilot-Users`

Deployment intent:

**Required**
