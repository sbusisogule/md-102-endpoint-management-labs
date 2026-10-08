# MD-102 Endpoint Management Labs

**Hands-on Microsoft Intune and Microsoft Entra ID enterprise endpoint management portfolio.**

This repository documents a hands-on Windows 11 endpoint management lab environment built to develop practical skills aligned with the **Microsoft MD-102: Endpoint Administrator** role.

The project covers identity, device enrollment, configuration, compliance, security, application deployment, Windows Update management, PowerShell remediation, and an integrated endpoint-management scenario.

---

## Project Overview

The lab environment was built around a Microsoft Entra ID tenant, Microsoft Intune, and a Windows 11 Enterprise test device.

### Environment

| Component           | Configuration                  |
| ------------------- | ------------------------------ |
| Identity            | Microsoft Entra ID             |
| Endpoint Management | Microsoft Intune               |
| License             | Microsoft 365 Business Premium |
| Test User           | `MD102 Test User`              |
| Pilot Group         | `MD102-Pilot-Users`            |
| Test Device         | `INTUNE-USER`                  |
| Operating System    | Windows 11 Enterprise          |
| Windows Version     | 25H2                           |
| OS Build            | `26200.6584`                   |
| Device Join         | Microsoft Entra joined         |
| Device Management   | Microsoft Intune               |

---

# Lab Portfolio

## Identity, Enrollment & Configuration

| Lab                | Topic                                  | Status   |
| ------------------ | -------------------------------------- | -------- |
| [LAB-00](./LAB-00) | Environment & GitHub Setup             | Complete |
| [LAB-01](./LAB-01) | Windows 11 Standard Configuration      | Complete |
| [LAB-02](./LAB-02) | Windows 11 Basic Compliance            | Complete |
| [LAB-03](./LAB-03) | Conditional Access                     | Complete |
| [LAB-04](./LAB-04) | Windows Hello for Business             | Complete |
| [LAB-05](./LAB-05) | Windows LAPS                           | Complete |
| [LAB-06](./LAB-06) | Microsoft Store Application Deployment | Complete |

## Endpoint Security

| Lab                | Topic                                | Status                    |
| ------------------ | ------------------------------------ | ------------------------- |
| [LAB-07](./LAB-07) | Microsoft Defender Antivirus         | Complete                  |
| [LAB-08](./LAB-08) | Windows Firewall                     | Complete                  |
| [LAB-09](./LAB-09) | Firewall RDP Rule                    | Complete                  |
| [LAB-10](./LAB-10) | Endpoint Security Policy             | Complete                  |
| [LAB-11](./LAB-11) | Windows Autopilot Deployment Profile | Complete                  |
| [LAB-12](./LAB-12) | Windows Autopilot Hardware Hash      | Complete                  |
| [LAB-13](./LAB-13) | Windows BitLocker                    | Complete                  |
| [LAB-14](./LAB-14) | Endpoint Security Baseline           | Complete                  |
| [LAB-15](./LAB-15) | Lab Documentation Status             | Documentation unavailable |

## Endpoint Analytics & Windows Management

| Lab                | Topic                                | Status     |
| ------------------ | ------------------------------------ | ---------- |
| [LAB-16](./LAB-16) | Windows Update Management            | Complete   |
| [LAB-17](./LAB-17) | Windows Update Compliance            | Complete   |
| [LAB-18](./LAB-18) | Endpoint Analytics                   | Complete   |
| [LAB-19](./LAB-19) | Windows Firewall Service Remediation | Configured |
| [LAB-20](./LAB-20) | Windows Update Ring                  | Configured |
| [LAB-21](./LAB-21) | Windows 11 Feature Update            | Configured |
| [LAB-22](./LAB-22) | Windows Update Compliance            | Complete   |

## Application Management & Automation

| Lab                | Topic                                    | Status     |
| ------------------ | ---------------------------------------- | ---------- |
| [LAB-23](./LAB-23) | Win32 Application Deployment & Detection | Complete   |
| [LAB-24](./LAB-24) | Windows Time Service Remediation         | Configured |

## Capstone

| Lab                | Topic                              | Status   |
| ------------------ | ---------------------------------- | -------- |
| [LAB-25](./LAB-25) | Final Integrated Endpoint Scenario | Complete |

---

# Technologies & Skills Demonstrated

### Microsoft Entra ID

* Microsoft Entra device join
* User and group management
* Device identity
* Entra-integrated Windows 11 enrollment

### Microsoft Intune

* Device enrollment
* Device management
* Configuration profiles
* Settings Catalog
* Compliance policies
* Application deployment
* Endpoint security policies
* Windows Update management
* Remediations
* Reporting and troubleshooting

### Windows 11

* Windows 11 Enterprise
* Windows 11 25H2
* Device registration and enrollment
* Secure Boot
* TPM
* Windows Hello
* Windows Firewall
* Windows Update
* BitLocker
* Windows LAPS

### Endpoint Security

* Microsoft Defender Antivirus
* Windows Defender Firewall
* Firewall rules
* Secure Boot
* TPM validation
* BitLocker
* Windows LAPS
* Conditional Access
* Device compliance

### Application Management

* Microsoft Store applications
* Win32 applications
* `.intunewin` packaging
* Microsoft Win32 Content Prep Tool
* Silent installation
* Uninstallation commands
* File-based detection rules
* Required application assignments

### PowerShell & Automation

* PowerShell detection scripts
* PowerShell remediation scripts
* Windows service management
* Exit-code based remediation logic
* Windows Firewall service remediation
* Windows Time service remediation

---

# Practical Endpoint Management Workflow

The labs were designed to demonstrate the lifecycle of a managed Windows endpoint:

```text
                    Microsoft Entra ID
                           |
                           v
                    User & Device Identity
                           |
                           v
                    Windows 11 Enrollment
                           |
                           v
                     Microsoft Intune
                           |
             +-------------+-------------+
             |             |             |
             v             v             v
       Configuration   Compliance    Applications
             |             |             |
             +-------------+-------------+
                           |
                           v
                    Endpoint Security
                           |
             +-------------+-------------+
             |             |             |
             v             v             v
         Defender      Firewall       BitLocker
             |             |             |
             +-------------+-------------+
                           |
                           v
                    Windows Updates
                           |
                           v
                     Remediation
                           |
                           v
                  Integrated Validation
```

---

# Final Integrated Scenario

**LAB-25** brings the individual technologies together into a single endpoint-management scenario.

The test device was validated for:

* Microsoft Entra join
* Microsoft Intune management
* Device compliance
* Secure Boot
* TPM readiness
* Windows Hello
* Windows Firewall
* Win32 application deployment
* Windows 11 25H2
* LAPS configuration

The final validation also demonstrated an important aspect of real-world administration: **not every Intune operation produces immediate reporting results**.

Where a configuration could not be fully validated, the limitation has been recorded rather than presenting an unverified result as successful.

---

# Troubleshooting & Real-World Lessons

Throughout the labs, the environment exposed several practical administration challenges.

### Intune reporting delays

Some policies remained in `Pending`, produced zero reporting records, or did not immediately appear on the endpoint.

The approach used was to document the observed state and continue with the next lab rather than artificially waiting for every Intune reporting cycle.

### Policy conflicts

The Windows Update Ring encountered a policy conflict during testing.

The conflicting earlier policy assignment was removed to reduce overlap and make the intended update-management configuration clearer.

### Application deployment

The first 7-Zip Win32 application configuration did not become ready for assignment.

The application was recreated using the correctly generated `.intunewin` package.

The resulting deployment was subsequently validated by confirming that 7-Zip was installed on the test device.

### LAPS validation

The LAPS policy was successfully configured, but direct password retrieval could not be fully validated because the required Microsoft Graph PowerShell components were not available in the test environment.

This is documented explicitly rather than being represented as a successful password retrieval.

### Endpoint Analytics

Endpoint Analytics was reviewed, but the tenant did not have sufficient data to produce meaningful device analytics.

The observed state was recorded rather than treated as an implementation failure.

---

# Evidence Structure

Each lab follows a consistent repository structure:

```text
LAB-XX/
├── README.md
├── Screenshots/
└── Evidence/
```

Where screenshots or additional evidence were not available, the folders are retained for consistency without inventing evidence.

---

# Repository Structure

```text
md-102-endpoint-management-labs/
│
├── README.md
│
├── LAB-00/
├── LAB-01/
├── LAB-02/
├── LAB-03/
├── LAB-04/
├── LAB-05/
├── LAB-06/
├── LAB-07/
├── LAB-08/
├── LAB-09/
├── LAB-10/
├── LAB-11/
├── LAB-12/
├── LAB-13/
├── LAB-14/
├── LAB-15/
├── LAB-16/
├── LAB-17/
├── LAB-18/
├── LAB-19/
├── LAB-20/
├── LAB-21/
├── LAB-22/
├── LAB-23/
├── LAB-24/
└── LAB-25/
```

---

# Portfolio Objective

The purpose of this repository is not simply to document Microsoft Learn exercises.

It demonstrates practical experience with:

**Identity → Enrollment → Configuration → Compliance → Security → Applications → Updates → Automation → Troubleshooting → Integrated Endpoint Management**

The project provides a foundation for progressing from guided MD-102 labs into real-world Microsoft Intune and Windows endpoint administration scenarios.

---

## Author

**Sbusiso Gule**

Microsoft Endpoint Management Lab Portfolio

Technologies:

`Microsoft Intune` · `Microsoft Entra ID` · `Windows 11` · `PowerShell` · `Microsoft 365`
