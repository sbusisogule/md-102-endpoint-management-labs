# LAB-24 — Windows Time Service Remediation

## Objective

Create an Intune Remediation that detects and automatically corrects an incorrectly configured Windows Time service on the MD-102 pilot device.

## Environment

* Platform: Windows 11
* Management: Microsoft Intune
* Pilot group: `MD102-Pilot-Users`
* Test device: `INTUNE-USER`
* Service: Windows Time (`W32Time`)

## Remediation Configuration

A remediation package was created in Microsoft Intune.

### Basics

* Name: `LAB-24-WIN11-Time-Service-Remediation`
* Description: `Detects and remediates the Windows Time service on the MD-102 pilot device.`
* Publisher: `Sbusiso Gule`

## Detection Script

The detection script checks whether the Windows Time service exists, is running, and is configured for automatic startup.

```powershell
$service = Get-Service -Name W32Time -ErrorAction SilentlyContinue

if ($null -eq $service) {
    Write-Output "Windows Time service was not found."
    exit 1
}

if ($service.Status -eq 'Running' -and $service.StartType -eq 'Automatic') {
    Write-Output "Windows Time service is running and set to Automatic."
    exit 0
}

Write-Output "Windows Time service requires remediation."
exit 1
```

Exit code `0` indicates that no remediation is required.

Exit code `1` indicates that remediation is required.

## Remediation Script

The remediation script configures the Windows Time service for automatic startup and starts the service if it is not already running.

```powershell
$service = Get-Service -Name W32Time -ErrorAction SilentlyContinue

if ($null -eq $service) {
    Write-Output "Windows Time service was not found."
    exit 1
}

Set-Service -Name W32Time -StartupType Automatic

if ($service.Status -ne 'Running') {
    Start-Service -Name W32Time
}

Write-Output "Windows Time service has been remediated."
exit 0
```

## Script Settings

* Run this script using the logged-on credentials: `No`
* Enforce script signature check: `No`
* Run script in 64-bit PowerShell host: `Yes`

## Assignments

* Scope: `Default`
* Included group: `MD102-Pilot-Users`
* Schedule: `Daily`

## Validation

The Intune Remediations dashboard showed the remediation configured with no devices currently reporting execution results at the time of documentation.

Detection status:

* Pending devices: `0`
* Without issues: `0`
* With issues: `0`
* Failed: `0`
* Not applicable: `0`

Remediation status:

* Non-targeted: `0`
* Issue fixed: `0`
* Recurred: `0`
* Failed: `0`

The lab therefore documents the remediation configuration rather than claiming that an Intune remediation execution was successfully reported.

## Result

LAB-24 demonstrated how Intune Remediations can be used to:

1. Detect an undesirable endpoint configuration.
2. Return an exit code indicating whether remediation is required.
3. Automatically correct the configuration with PowerShell.
4. Target the remediation to a pilot group.
5. Schedule recurring compliance checks.

## Evidence

Supporting material can be placed in:

* `Screenshots/`
* `Evidence/`

## Notes

The remediation was configured successfully. Intune had not populated execution results at the time of documentation, so no successful remediation run is claimed.
