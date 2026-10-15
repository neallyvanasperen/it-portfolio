# TSG-001: Device Not Compliant

| | |
|---|---|
| **Version** | 0.1 (Draft) |
| **Owner** | |
| **Last reviewed** | |

## Symptom
A device shows as "Not compliant" in Intune, or the user is blocked from company apps.

## Check in order
1. **Which setting failed?** Intune > Devices > the device > Device compliance > open the policy and read which setting shows as not compliant.
2. **Has the device checked in recently?** Check the last check-in time. If it is old, sync the device.
3. **Is the device encrypted?** (BitLocker on Windows, encryption on Android.)
4. **Is the OS up to date?** Compare against the minimum version in the compliance policy.
5. **Is a passcode set?**
6. **Is the right policy assigned?** Check the device is in the expected group.

## Common causes and fixes
| Cause | Fix |
|---|---|
| Device not checked in | Sync from Intune or from the device |
| Encryption not on | Enable it, then sync |
| OS out of date | Update, then sync |
| Wrong group membership | Fix group or naming, wait for dynamic group to update |
| Conflicting policies | Review overlapping assignments |

## Escalate if
The device meets every requirement but still shows not compliant after a sync and a 24-hour wait.

## Revision history
| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | | Initial draft | |
