# LAB-12 — Windows Autopilot Hardware Hash Collection

## Objective

Document the Windows Autopilot hardware-hash collection process used to prepare a Windows device for Autopilot registration.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise
* Test device: `INTUNE-USER`
* Pilot environment: `MD102-Pilot-Users`

## Scenario

Windows Autopilot uses device-specific hardware information to identify and register Windows devices.

This lab focused on the hardware-information collection stage of the Autopilot workflow rather than claiming successful registration of the already-enrolled test VM.

## Hardware Hash Collection

The Windows Autopilot information script was used as the collection method:

```powershell
Get-WindowsAutopilotInfo.ps1
```

The documented output location was:

```text
C:\AutopilotHWID.csv
```

The resulting hardware information is device-specific and should not be committed to a public GitHub repository.

## Registration Workflow

The collected hardware information represents the type of information used during Windows Autopilot device registration.

The lab intentionally does **not** claim that `INTUNE-USER` was successfully registered as an Autopilot device.

This distinction is important because the test VM was already enrolled and managed through Microsoft Entra ID and Intune. Autopilot registration and deployment are separate stages of the endpoint lifecycle.

## Security Considerations

Hardware-hash information is specific to a device and should be treated as sensitive device-registration information.

The hardware hash and generated CSV were therefore not included in this public repository.

## Skills Demonstrated

* Windows Autopilot fundamentals
* Hardware-hash collection
* PowerShell administration
* Windows device identification
* Autopilot registration workflow
* Handling device-specific registration information
* Protecting device-specific registration data

## Outcome

LAB-12 documented the Windows Autopilot hardware-hash collection workflow and the role of the collected information in the device-registration process.

The lab does not claim successful Autopilot registration or deployment of `INTUNE-USER`.

## Evidence Status

**Status: Collection Process Documented**

The repository intentionally excludes the device-specific hardware hash and generated CSV.
