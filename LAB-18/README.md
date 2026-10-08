# LAB-18 — Endpoint Analytics

## Objective

Use Microsoft Intune Endpoint analytics to monitor endpoint performance, evaluate the user experience, and review available recommendations.

## Environment

* Microsoft Intune
* Microsoft Entra ID
* Windows 11 Enterprise 25H2
* Test device: `INTUNE-USER`

## Endpoint Analytics Overview

The Endpoint analytics overview was reviewed to evaluate the available endpoint performance data.

At the time of validation:

| Metric                   | Result            |
| ------------------------ | ----------------- |
| Endpoint analytics score | 0                 |
| Baseline                 | 16                |
| Status                   | Insufficient data |

The score of zero was not interpreted as an endpoint failure. Endpoint Analytics requires sufficient telemetry and device population data before meaningful organizational analytics can be produced.

## Device Scores

The Device scores section showed:

* Devices: `0`
* `INTUNE-USER`: Not listed

This indicated that the test environment did not yet have sufficient Endpoint Analytics data available for device-level scoring.

## Model Scores

Model scores showed:

`No results`

The environment did not have sufficient data to generate model-level results.

## Anomalies

The anomaly section was reviewed.

| Severity      | Result |
| ------------- | -----: |
| High          |      0 |
| Medium        |      0 |
| Low           |      0 |
| Informational |      0 |
| Total         |      0 |

No endpoint anomalies were reported during the validation period.

## Advanced Analytics

The Endpoint Analytics interface displayed information regarding the Advanced Analytics add-on.

The lab environment did not require enabling the add-on because the objective was to evaluate the standard Endpoint Analytics experience.

## Validation

Endpoint Analytics was successfully accessed and reviewed through Microsoft Intune.

The available results showed that the tenant did not yet have sufficient telemetry or device population for meaningful endpoint scoring.

This is an important administrative observation: an Endpoint Analytics score of zero with an **Insufficient data** status does not necessarily indicate poor endpoint health.

## Administrative Considerations

Endpoint Analytics becomes more useful as an organization accumulates endpoint telemetry.

An administrator should distinguish between:

* A genuinely poor endpoint score
* Missing or insufficient telemetry
* An insufficient number of devices
* A newly configured environment

This prevents missing analytics data from being incorrectly interpreted as an endpoint-health failure.

## Skills Demonstrated

* Microsoft Intune Endpoint Analytics
* Endpoint performance monitoring
* User-experience analysis
* Endpoint score interpretation
* Telemetry awareness
* Anomaly monitoring
* Intune troubleshooting and reporting

## Outcome

LAB-18 demonstrated how Endpoint Analytics can be used to monitor Windows endpoint performance and user experience.

The lab also demonstrated an important troubleshooting principle:

> **Insufficient data is different from a poor endpoint-health result.**

The Endpoint Analytics interface and available reporting data were reviewed successfully, but the environment did not yet contain sufficient telemetry for meaningful endpoint scoring.

## Evidence Status

**Status: Reviewed / Insufficient Data**

Endpoint Analytics was accessed and evaluated, but meaningful device-level analytics were not available in the test environment.
