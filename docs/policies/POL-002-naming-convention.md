# POL-002: Naming Convention

| | |
|---|---|
| **Version** | 0.1 (Draft) |
| **Owner** | [IT lead] |
| **Last reviewed** | |

## 1. Purpose
Consistent names make objects easy to find, target and audit.

## 2. Standards

| Object | Pattern | Example |
|---|---|---|
| User | `first.last` | `sam.lee` |
| Admin account | `adm-first.last` | `adm-sam.lee` |
| Service account | `svc-<purpose>` | `svc-backup` |
| AD security group (department) | `SG-<Dept>-Staff` | `SG-Operations-Staff` |
| AD security group (resource) | `SG-<Resource>-<RW/RO>` | `SG-Procurement-Share-RW` |
| Entra group (users) | `ENT-<Purpose>` | `ENT-Operations-Users` |
| Entra group (devices) | `ENT-Dev-<Type>` | `ENT-Dev-Win-Laptops` |
| App access group | `ENT-App-<App>-Users` | `ENT-App-Odoo-Users` |
| On-prem PC | `JM-PC-###` | `JM-PC-001` |
| Laptop | `JM-LT-###` | `JM-LT-001` |
| Android phone | `JM-AP-###` | `JM-AP-001` |
| Orders tablet | `JM-TO-###` | `JM-TO-001` |
| Clock-in tablet | `JM-TC-###` | `JM-TC-001` |
| GPO | `GPO-<Scope>-<Purpose>` | `GPO-Laptops-Desktop-Restrictions` |
| Intune policy | `<Platform>-<Type>-<Purpose>` | `Win-Compliance-Baseline` |

## 3. Rules
- Names must be unique and follow the pattern exactly.
- Do not reuse a retired device name until it has been removed from all systems.
- Changes to this convention are recorded in the revision history.

## Revision history
| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | | Initial draft | |
