# 03 Build Plan and Verification

Tick each phase as completed and add notes and screenshots (redacted).

## Phase 1: Active Directory foundation
- [ ] Promote DC01, configure DNS
- [ ] DHCP scope for the lab network
- [ ] Create OU structure from [01-structure](01-structure.md)
- [ ] Verification: `dcdiag`, DNS resolves the domain

## Phase 2: Users, groups, permissions
- [ ] Create test users in department OUs
- [ ] Create `SG-` department and resource groups, nest them
- [ ] Create `adm-` accounts and delegate password reset to helpdesk
- [ ] File shares on FS01 with group-based permissions
- [ ] Verification: a test user can open their department share and not others

## Phase 3: Group Policy baseline
- [ ] Desktop restrictions, drive mappings, password policy
- [ ] Verification: `gpresult /r` on a domain-joined client

## Phase 4: Sync to Entra ID
- [ ] Add `onmicrosoft.com` UPN suffix, set user UPNs
- [ ] Install Entra Connect on SYNC01, enable password hash sync
- [ ] Filter sync scope to the `JimMakers` OU only
- [ ] Verification: users appear in Entra as "synced from on-premises"

## Phase 5: Hybrid join
- [ ] Configure hybrid Entra join in Entra Connect
- [ ] Join a Windows client to the domain and confirm it registers in Entra
- [ ] Verification: device shows as "Microsoft Entra hybrid joined"

## Phase 6: Intune
- [ ] Create `ENT-` cloud groups (dynamic where useful)
- [ ] Enrol devices (auto-enrol via policy for hybrid devices)
- [ ] Compliance policy, update ring, BitLocker profile
- [ ] Deploy a test app
- [ ] Verification: device shows compliant; policy and app arrive

## Phase 7: Conditional Access and roles
- [ ] Assign Entra and Intune admin roles per the [role matrix](02-role-matrix.md)
- [ ] Create and test break-glass account
- [ ] Conditional Access: require MFA, require compliant device (pilot group first)
- [ ] Verification: sign-in tests with each role

## Phase 8: Conflict check
- [ ] Review each setting against the policy ownership table in the README
- [ ] Confirm no setting is controlled by both Group Policy and Intune

## Moving to a real environment (checklist)
- [ ] Audit existing OUs, groups, GPOs, users and role assignments, and export or screenshot them first
- [ ] Map lab objects to real ones (kept in a private mapping file, not this repo)
- [ ] Confirm licensing supports each feature in use
- [ ] Create break-glass account before changing any Conditional Access
- [ ] Pilot with 1-2 users or a test group
- [ ] Roll out in stages, communicate changes to staff
- [ ] Record actual changes in the company's own documentation
