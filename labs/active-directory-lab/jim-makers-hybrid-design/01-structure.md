# 01 Structure: OUs, Groups, Naming

## OU structure (Active Directory)

```
corp.jimmakers.lab
└── JimMakers
    ├── Users
    │   ├── Operations
    │   ├── Procurement
    │   ├── AdminFinance
    │   ├── IT
    │   └── ServiceAccounts
    ├── Admin            (separate adm- accounts, never synced to cloud admin roles beyond need)
    ├── Groups
    │   ├── Security
    │   └── Distribution
    ├── Computers
    │   ├── Workstations
    │   ├── Laptops
    │   └── Shared-Kiosk
    └── Servers
```

Why this shape: OUs mirror how GPOs will be applied (by department for users, by device type for computers), and the Entra Connect sync scope can be filtered to the `JimMakers` OU only.

## Naming conventions

| Object | Pattern | Example |
|---|---|---|
| User | `first.last` | `sam.lee` |
| Admin account | `adm-first.last` | `adm-sam.lee` |
| Service account | `svc-<purpose>` | `svc-backup` |
| AD security group (department) | `SG-<Dept>-Staff` | `SG-Operations-Staff` |
| AD security group (resource) | `SG-<Resource>-<RW/RO>` | `SG-Procurement-Share-RW` |
| Entra cloud group (Intune target) | `ENT-<Purpose>` | `ENT-Intune-Windows-Laptops` |
| Computer | `JM-<type>-<number>` | `JM-LT-001` |
| GPO | `GPO-<Scope>-<Purpose>` | `GPO-Laptops-Desktop-Restrictions` |

## Group design

- **Department group** (`SG-Operations-Staff`) is the main group each user belongs to.
- **Resource groups** (`SG-...-RW/RO`) get the permissions on shares and servers. Department groups are nested into resource groups, not users directly.
- **Entra cloud groups** can be dynamic (e.g. all Windows devices, or users in a department) and are used for Intune policies and app assignment.

## UPN note for the lab

A lab domain like `corp.jimmakers.lab` cannot be verified in Entra. Add the tenant's `onmicrosoft.com` name as an alternate UPN suffix in AD Domains and Trusts, and give lab users that suffix so they sync cleanly. In a real company, use their verified public domain instead.
