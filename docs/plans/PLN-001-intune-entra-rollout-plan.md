# PLN-001: Intune and Entra Rollout Plan

| | |
|---|---|
| **Version** | 0.1 (Draft) |
| **Owner** | [IT lead, fictional] |
| **Last reviewed** | |
| **Related** | [Goals and requirements](../../labs/jim-makers-hybrid-design/00-goals-and-requirements.md), [Device types](../../labs/jim-makers-hybrid-design/04-device-types.md) |

## 1. Purpose
Describe how device and identity management will be rolled out for Jim Makers, in phases, with checks and a way back at each stage.

## 2. Scope
**In scope:** on-prem PCs, remote laptops, company Android phones, Android kiosk tablets, directors' personal iPads and laptops.
**Out of scope:** [list anything excluded, e.g. macOS, servers]

## 3. Objectives
- 
- 

## 4. Current state
[What exists today: OUs, groups, GPOs, licensing, devices. Record before changing anything.]

## 5. Target state
[Summarise the design: who owns what between AD, Entra and Intune.]

## 6. Phases

| Phase | What | Pilot group | Success criteria | Rollback |
|---|---|---|---|---|
| 1 | Prepare tenant, groups, licensing | IT only | Groups populate correctly | Delete test groups |
| 2 | Windows device enrolment | 2-3 devices | Devices enrol and report compliant | Retire devices from Intune |
| 3 | Android phones and kiosks | 1-2 devices each | Policies and apps arrive | Wipe and re-enrol |
| 4 | Directors' app protection | 1 director | Access works, MFA prompts | Remove policy assignment |
| 5 | Conditional Access | Pilot group, then all | Compliant users unaffected | Set policy to report-only or off |

## 7. Roles and responsibilities
| Role | Responsibility |
|---|---|
| IT lead | Approves changes, owns the plan |
| Helpdesk | Performs routine procedures, escalates issues |
| Interns | Perform SOPs under supervision |

## 8. Risks
| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Admin lockout from a Conditional Access mistake | Medium | High | Break-glass account, report-only mode first |
| Users disrupted by new policy | Medium | Medium | Pilot, communicate in advance |
| Licensing doesn't cover a feature | Medium | Medium | Check before rollout |

## 9. Communication
[Who is told what, and when.]

## 10. Verification and sign-off
[How completion will be confirmed.]

## Revision history
| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | | Initial draft | |
