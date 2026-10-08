# LAB-23 — Win32 Application Deployment & Detection

## Objective

Package, deploy, and configure detection for a Win32 application using Microsoft Intune.

## Environment

* Platform: Windows 11
* Management: Microsoft Intune
* Pilot group: `MD102-Pilot-Users`
* Test device: `INTUNE-USER`
* Application: 7-Zip
* Package version: `7z2604-x64.exe`

## Application Source

The official 7-Zip x64 installer was downloaded to the Windows 11 lab VM.

The lab source structure was:

```text
C:\MD102\
├── LAB-23\
│   └── Source\
│       └── 7z2604-x64.exe
└── Tools\
    └── IntuneWinAppUtil.exe
```

## Win32 Package Creation

The Microsoft Win32 Content Prep Tool was used to convert the installer into an Intune Win32 application package.

The following source and output locations were used:

* Source folder: `C:\MD102\LAB-23\Source`
* Setup file: `7z2604-x64.exe`
* Output folder: `C:\MD102\LAB-23`
* Catalog folder: `N`

The package was successfully created at 100% completion.

Generated package:

```text
7z2604-x64.intunewin
```

## Intune Application Configuration

### Application information

* Name: `7-Zip`
* Description: `7-Zip file compression utility for Windows 11 lab devices.`
* Publisher: `7-Zip`
* Developer: `Igor Pavlov`
* Category: `Productivity`

### Program configuration

Install command:

```text
7z2604-x64.exe /S
```

Uninstall command:

```text
"%ProgramFiles%\7-Zip\Uninstall.exe" /S
```

* Install behavior: `System`
* Device restart behavior: App install may force a device restart

### Requirements

* Operating system architecture: `x64`
* Minimum operating system: Windows 10 1607 or later

## Detection Rule

A file-based detection rule was configured:

* Path:

```text
C:\Program Files\7-Zip\7zFM.exe
```

* Detection method: File or folder exists
* Associated 64-bit setting: Not configured as a 32-bit application on 64-bit systems

This allows Intune to determine whether the 7-Zip application is installed.

## Assignment

The application was configured as:

* Assignment type: `Required`
* Target group: `MD102-Pilot-Users`

The Intune application page subsequently showed the application as assigned.

## Validation

The 7-Zip application was later confirmed as installed on the Windows 11 test VM during the final integrated scenario.

This provided practical validation of the Win32 deployment and detection configuration.

## Troubleshooting

The first application deployment attempt did not become ready for assignment and displayed an application readiness message.

The initial application was deleted and recreated using the correctly generated `.intunewin` package.

The second configuration was successfully assigned to the pilot group.

The lab was not dependent on waiting for Intune deployment reporting to complete before continuing with the remaining labs.

## Result

LAB-23 demonstrated the complete Win32 application management workflow:

1. Obtain an application installer.
2. Prepare the application source.
3. Create an `.intunewin` package.
4. Configure the application in Intune.
5. Define silent installation and uninstall commands.
6. Configure application requirements.
7. Configure file-based detection.
8. Assign the application to a pilot group.
9. Validate installation on the Windows 11 test device.

## Evidence

Supporting material can be placed in:

* `Screenshots/`
* `Evidence/`

## Notes

This lab demonstrates application lifecycle management using Microsoft Intune and provides practical experience with Win32 application packaging, deployment, assignment, and detection.
