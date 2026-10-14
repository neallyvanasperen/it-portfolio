# 02 Role Matrix

## Administrative roles

| Person (fictional) | Account | Role / system | Why |
|---|---|---|---|
| IT lead | `adm-sam.lee` | Domain Admins (AD), Intune Administrator, User Administrator | Runs the environment |
| Helpdesk | `adm-jo.park` | Delegated password reset on Users OU, Entra Helpdesk Administrator, Intune Help Desk Operator | Day-to-day support, no wipe or policy changes |
| Break-glass | `breakglass01` | Entra Global Administrator (cloud-only) | Emergency access only; excluded from Conditional Access; password stored offline |

Principles: least privilege, separate admin accounts, one or two Global Administrators at most, break-glass tested and monitored.

## Staff access (by group)

| Department | AD group | Shares / servers | Entra / Intune group | Gets via Intune |
|---|---|---|---|---|
| Operations | `SG-Operations-Staff` | Operations share RW, ERP access | `ENT-Operations-Users` | Standard apps, laptop profile |
| Procurement | `SG-Procurement-Staff` | Procurement share RW | `ENT-Procurement-Users` | Standard apps, laptop profile |
| Admin/Finance | `SG-AdminFinance-Staff` | Finance share RW | `ENT-AdminFinance-Users` | Standard apps, stricter compliance |
| IT | `SG-IT-Staff` | All shares RO, server access | `ENT-IT-Users` | Admin tools |

## Policy targeting

| Policy | Targets | Owner |
|---|---|---|
| Desktop restrictions | `JimMakers/Computers/Laptops` OU | Group Policy |
| Drive mappings | Department groups | Group Policy |
| Windows Update ring | `ENT-Intune-Windows-Laptops` | Intune |
| BitLocker | `ENT-Intune-Windows-Laptops` | Intune |
| Compliance policy | `ENT-Intune-Windows-Laptops` | Intune |
| MFA / Conditional Access | `ENT-*-Users` (excluding break-glass) | Entra |
