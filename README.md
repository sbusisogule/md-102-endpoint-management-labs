# MD-102 Endpoint Management Labs

Hands-on Microsoft Intune and Microsoft Entra ID enterprise endpoint management lab.

## Lab 00 — Environment & GitHub Setup

### Objective

Build and validate a Microsoft Intune and Microsoft Entra ID test environment for hands-on MD-102 endpoint management training.

### Environment

| Component | Configuration |
|---|---|
| Microsoft Entra ID | Configured |
| Microsoft Intune | Configured |
| License | Microsoft 365 Business Premium |
| Test user | MD102 Test User |
| Security group | MD102-Pilot-Users |
| Windows VM | INTUNE-USER |
| Windows edition | Windows 11 Enterprise |
| Windows version | 25H2 |
| OS build | 26200.6584 |

### Enrollment Configuration

- MDM user scope: **All**
- Windows MDM enrollment: **Allowed**
- Minimum Windows version: **Not configured**
- Maximum Windows version: **Not configured**
- Automatic enrollment: **Enabled through Microsoft Entra join**

### Device Enrollment Validation

The Windows 11 test VM was successfully joined to Microsoft Entra ID.

`dsregcmd /status` confirmed:

- AzureAdJoined: **YES**
- DomainJoined: **NO**
- WorkplaceJoined: **NO**

The device successfully synchronized with the management service.

### Intune Validation

The device appeared in Microsoft Intune with:

- Device name: **INTUNE-USER**
- Managed by: **Intune**
- Ownership: **Corporate**
- Compliance: **Compliant**
- Primary user: **MD102 Test User**
- OS build: **26200.6584**

### Architecture

```text
MD102 Test User
       |
       v
Microsoft Entra ID
       |
       | Microsoft Entra Join
       v
Windows 11 Enterprise
       |
       | Automatic MDM Enrollment
       v
Microsoft Intune
       |
       +-- Device Management
       +-- Configuration
       +-- Compliance
       +-- Applications
       +-- Endpoint Security
