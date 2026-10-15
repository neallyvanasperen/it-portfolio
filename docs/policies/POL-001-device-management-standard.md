# POL-001: Device Management Standard

| | |
|---|---|
| **Version** | 0.1 (Draft) |
| **Owner** | [IT lead] |
| **Applies to** | All devices accessing Jim Makers systems |
| **Last reviewed** | |

## 1. Purpose
Define how each type of device is owned, enrolled and controlled.

## 2. Standards by device type

| Device | Ownership | Enrolment | Management | Who may use it |
|---|---|---|---|---|
| On-prem PC | Company | Hybrid joined, automatic Intune enrolment | Intune + Group Policy | Staff with an AD account |
| Remote laptop | Company | Entra joined via Autopilot | Intune | Assigned user only |
| Company Android phone | Company | Android Enterprise, fully managed | Intune | Assigned user only |
| Orders tablet | Company | Android dedicated, kiosk | Intune | Shared, operators |
| Clock-in tablet | Company | Android dedicated, single app | Intune | Shared, no sign-in |
| Director iPad / laptop | Personal | Registered / app protection | App protection only | Owner |

## 3. Requirements
- All company devices must be encrypted and enrolled before use.
- Company devices must meet compliance policy to access company data.
- Personal devices are not enrolled; company data is protected inside approved apps.
- Lost or stolen devices must be reported to IT immediately.

## 4. Ownership of settings
Each setting is controlled by one system only. See the ownership table in the [hybrid design](../../labs/jim-makers-hybrid-design/README.md).

## 5. Exceptions
Exceptions require approval from the IT lead and are recorded here.

## Revision history
| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | | Initial draft | |
