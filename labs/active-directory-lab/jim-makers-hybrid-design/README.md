# Jim Makers: Hybrid Identity & Endpoint Design

**Status:** In progress
**Scenario:** A small fictional manufacturing company ("Jim Makers") running on-premises Active Directory, synced to Microsoft Entra ID, with devices managed by Intune.
**Why this exists:** To design and prove a hybrid structure in a lab first, so it can be reproduced one-to-one in a real small-business environment.

## Design principle

Each system owns a clear job. If two systems try to do the same job, they conflict, so the split is decided up front.

| Layer | Owns | Does NOT own |
|---|---|---|
| **Active Directory (on-prem)** | User, group and computer accounts (source of truth); sign-in to on-prem resources (file shares, ERP/app servers); Group Policy for domain-joined PCs and servers; DNS and DHCP | Cloud app access, MFA, device compliance |
| **Entra Connect (sync)** | Copies users, groups and password hashes from AD up to Entra ID | Editing identities (it only mirrors) |
| **Microsoft Entra ID** | Cloud identity and licensing; MFA and Conditional Access; single sign-on to cloud apps; cloud-only admin roles; device registration | On-prem file permissions, GPOs |
| **Intune** | Device enrolment; compliance; configuration profiles; app deployment; update rings; BitLocker; remote wipe | User creation, on-prem access |

## Golden rules for the hybrid

1. **Create and edit synced users in AD, not in Entra.** Synced users are mastered on-prem. Changing them in the cloud either fails or gets overwritten.
2. **Two kinds of groups:**
   - AD security groups (`SG-`) control on-prem access (shares, servers).
   - Entra cloud groups (`ENT-`) control Intune targeting and cloud app access.
3. **Don't set the same setting in both Group Policy and Intune.** Pick one owner per setting and record it in the policy ownership table below.
4. **Admin accounts are separate from daily accounts** (`adm-` prefix), and only a few people hold powerful roles.
5. **Sync only what's needed** by filtering the OUs that Entra Connect syncs.

## Policy ownership (decide per setting)

| Setting area | Owner | Reason |
|---|---|---|
| Password policy | AD | Source of truth on-prem; syncs as password hash |
| Drive mappings, printers | Group Policy | Needs on-prem resources |
| Desktop restrictions | Group Policy | Established GPO baseline |
| BitLocker | Intune | Cloud key escrow and reporting |
| Windows Update rings | Intune | Controlled rollout and reporting |
| Compliance and Conditional Access | Intune + Entra | Cloud-only features |
| App deployment (Win32/Store) | Intune | Central, reportable |
| MFA | Entra | Cloud feature |

## Contents

- [01 Structure (OUs, groups, naming)](01-structure.md)
- [02 Role matrix](02-role-matrix.md)
- [03 Build plan and verification](03-build-plan.md)

## Lab environment

| Item | Detail |
|---|---|
| Hypervisor | Proxmox |
| Domain | `corp.jimmakers.lab` (fictional) |
| Tenant | Free trial (not published) |
| Servers | DC01 (AD DS, DNS, DHCP), SYNC01 (Entra Connect), FS01 (file server) |
| Clients | Windows VMs for hybrid join and Intune enrolment tests |

## Troubleshooting log

| Date | Symptom | Cause | Fix |
|---|---|---|---|
| | | | |

## What I learned
- 
