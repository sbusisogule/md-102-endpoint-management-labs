# LAB-12 — Windows Autopilot Hardware Hash Collection

## Objective

Collect a Windows device's hardware hash for use in the Windows Autopilot device registration workflow.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise
* Test device: `INTUNE-USER`
* Pilot environment: `MD102-Pilot-Users`

## Scenario

Windows Autopilot uses device-specific hardware information to identify and register Windows devices.

This lab demonstrates the hardware-hash collection process without importing an already-enrolled VM directly into the Autopilot device list.

## Hardware Hash Collection

The Windows Autopilot information script was used to collect the device hardware information.

The following PowerShell script was used:

```powershell
Get-WindowsAutopilotInfo.ps1
```

The resulting hardware information was exported to:

```text
C:\AutopilotHWID.csv
```

## CSV Validation

The generated CSV was reviewed to confirm that the expected Autopilot registration information was present.

The CSV contained fields including:

* Device Serial Number
* Windows Product ID
* Hardware Hash

The hardware hash was not published in this repository because it is device-specific information.

## Registration Workflow

The collected CSV represents the information that can be used when registering a physical or virtual Windows device with Windows Autopilot.

The lab demonstrates the collection stage of the Autopilot registration workflow rather than claiming that the test VM was successfully registered as an Autopilot device.

## Skills Demonstrated

* Windows Autopilot fundamentals
* Hardware-hash collection
* PowerShell administration
* Windows device identification
* Autopilot registration workflow
* Handling device-specific registration information securely

## Outcome

LAB-12 successfully demonstrated how to collect the Windows Autopilot hardware hash and export the required device information to a CSV file.

The generated `C:\AutopilotHWID.csv` contained the expected registration fields. The device-specific hardware hash was intentionally excluded from the GitHub repository.
