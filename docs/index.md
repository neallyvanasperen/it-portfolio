# Documentation Index

Implementation plans, policies and procedures for the fictional company **Jim Makers** (hybrid Active Directory, Entra ID and Intune environment). Written so that helpdesk staff and interns can follow them.

Design background: [labs/jim-makers-hybrid-design](../labs/jim-makers-hybrid-design/)

## How the documents fit together

| Type | Answers | Reader |
|---|---|---|
| Plan | How will we roll this out? | IT lead, management |
| Policy | What are the rules, and why? | Everyone |
| SOP | What exact steps do I follow? | Helpdesk, interns |
| Troubleshooting | What do I check when it fails? | Helpdesk |

## Document register

### Plans
| ID | Title | Version | Status | Last reviewed |
|---|---|---|---|---|
| PLN-001 | [Intune and Entra rollout plan](plans/PLN-001-intune-entra-rollout-plan.md) | 0.1 | Draft | |

### Policies and standards
| ID | Title | Version | Status | Last reviewed |
|---|---|---|---|---|
| POL-001 | [Device management standard](policies/POL-001-device-management-standard.md) | 0.1 | Draft | |
| POL-002 | [Naming convention](policies/POL-002-naming-convention.md) | 0.1 | Draft | |
| POL-003 | [Administrative access policy](policies/POL-003-administrative-access-policy.md) | 0.1 | Draft | |

### Procedures (SOPs)
| ID | Title | Version | Status | Tested by |
|---|---|---|---|---|
| SOP-001 | [Create a new user](sops/SOP-001-create-new-user.md) | 0.1 | Draft | |
| SOP-002 | [Enrol a Windows laptop with Autopilot](sops/SOP-002-autopilot-laptop.md) | 0.1 | Draft | |
| SOP-003 | [Enrol a company Android phone](sops/SOP-003-android-phone.md) | 0.1 | Draft | |
| SOP-004 | [Provision a kiosk tablet](sops/SOP-004-kiosk-tablet.md) | 0.1 | Draft | |
| SOP-005 | [Retire or wipe a device](sops/SOP-005-retire-device.md) | 0.1 | Draft | |

### Troubleshooting guides
| ID | Title | Version | Status |
|---|---|---|---|
| TSG-001 | [Device not compliant](troubleshooting/TSG-001-device-not-compliant.md) | 0.1 | Draft |

## Status key
- **Draft:** written but not yet tested
- **Tested:** followed start to finish from a clean state, with fixes applied
- **Approved:** reviewed and in use

## Rules for these documents
1. Test every procedure from a clean state using only what is written.
2. Use fictional names, tenant details and addresses only. Blur real details in screenshots.
3. Write steps in your own words; do not copy vendor documentation.
4. Update the version and revision history whenever a document changes.
5. Keep each document to one or two pages where possible.
