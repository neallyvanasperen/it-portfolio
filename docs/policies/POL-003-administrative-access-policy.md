# POL-003: Administrative Access Policy

| | |
|---|---|
| **Version** | 0.1 (Draft) |
| **Owner** | [IT lead] |
| **Last reviewed** | |

## 1. Purpose
Limit administrative power to what each person needs, and make sure it can be audited.

## 2. Principles
- **Least privilege:** grant the narrowest role that does the job.
- **Separate accounts:** administrators use an `adm-` account for admin work and a normal account for everyday work.
- **Few Global Administrators:** no more than two named accounts, plus the break-glass account.
- **Break-glass account:** cloud-only, long password stored offline, excluded from Conditional Access, tested on a schedule, sign-ins alerted.

## 3. Role assignment

| Role | Held by | Purpose | Review |
|---|---|---|---|
| Domain Admin (AD) | IT lead | Run the domain | Quarterly |
| Helpdesk Administrator (Entra) | Helpdesk | Password resets, basic support | Quarterly |
| Intune Help Desk Operator | Helpdesk | View devices, run remote actions | Quarterly |
| Intune Administrator | IT lead | Manage policies | Quarterly |

## 4. Requests and approval
1. Request made to the IT lead with a reason.
2. IT lead approves and records it.
3. Access is assigned and logged.
4. Access is removed when no longer needed.

## 5. Review
Role holders are reviewed every quarter. Unused access is removed.

## Revision history
| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | | Initial draft | |
