# LAB-19 — Windows Firewall Service Remediation

## Objective

Create a Microsoft Intune Remediation that detects and remediates the Windows Firewall service on a managed Windows 11 endpoint.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`
* Pilot group: `MD102-Pilot-Users`
* PowerShell
* Intune Remediations

## Scenario

A Windows endpoint may have the Windows Firewall service stopped or configured incorrectly.

This lab demonstrates a practical endpoint-management approach where Intune can automatically detect the problem and execute a remediation script.

## Detection Script

The detection script checks the Windows Firewall service (`MpsSvc`).

The expected state is:

* Service exists
* Service status: `Running`
* Startup type: `Automatic`

A compliant endpoint returns exit code `0`.

An endpoint requiring remediation returns exit code `1`.

Example logic:

```powershell
$service = Get-Service -Name MpsSvc -ErrorAction SilentlyContinue

if ($null -eq $service) {
    Write-Output "Windows Firewall service was not found."
    exit 1
}

if ($service.Status -eq 'Running' -and $service.StartType -eq 'Automatic') {
    Write-Output "Windows Firewall service is running and set to Automatic."
    exit 0
}

Write-Output "Windows Firewall service requires remediation."
exit 1
```

## Remediation Script

The remediation script sets the Windows Firewall service startup type to Automatic and starts the service if it is not already running.

```powershell
$service = Get-Service -Name MpsSvc -ErrorAction SilentlyContinue

if ($null -eq $service) {
    Write-Output "Windows Firewall service was not found."
    exit 1
}

Set-Service -Name MpsSvc -StartupType Automatic

if ($service.Status -ne 'Running') {
    Start-Service -Name MpsSvc
}

Write-Output "Windows Firewall service has been remediated."
exit 0
```

## Assignment

The remediation was assigned to:

```text
MD102-Pilot-Users
```

The scripts were configured to:

* Run using the system context
* Not enforce script signature checking
* Run in 64-bit PowerShell

## Endpoint Validation

The Windows Firewall service was checked on the Windows 11 test VM.

The service was already in the expected state:

* Status: `Running`
* Startup type: `Automatic`

Because the endpoint was already compliant, there was no need for the remediation to make a corrective change.

## Intune Reporting

The Intune Remediations dashboard showed:

### Detection

* Pending devices: `0`
* Without issues: `0`
* With issues: `0`
* Failed: `0`
* Not applicable: `0`

### Remediation

* Non-targeted: `0`
* Issue fixed: `0`
* Recurred: `0`
* Failed: `0`

The reporting state was treated as **configured but not yet executed/reported**, rather than waiting indefinitely for Intune telemetry.

## Administrative Lesson

Remediations are particularly useful for maintaining desired endpoint states.

The detection script determines whether the device is compliant. The remediation script only needs to act when the desired state is not present.

This creates an automated workflow:

```text
Detect
   ↓
Compliant?
 ┌─┴─┐
Yes  No
 ↓    ↓
Done Remediate
        ↓
      Verify
```

## Skills Demonstrated

* Microsoft Intune Remediations
* PowerShell scripting
* Windows service administration
* Detection and remediation logic
* System-context execution
* 64-bit PowerShell
* Endpoint troubleshooting
* Desired-state configuration concepts

## Outcome

LAB-19 demonstrated how Microsoft Intune Remediations can automatically detect and correct an unhealthy Windows Firewall service configuration.

The test VM was already in the desired state, with `MpsSvc` running and configured for Automatic startup.

The remediation was therefore configured and validated without artificially breaking the endpoint simply to force a remediation event.
