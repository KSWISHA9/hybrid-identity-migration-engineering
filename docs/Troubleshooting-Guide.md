# Hybrid Identity Troubleshooting Guide

## Duplicate UPN

Symptoms:
- Export errors
- Duplicate sign-in names

Resolution:
- Identify conflicting objects
- Correct UPN
- Run Delta Sync

---

## Duplicate proxyAddresses

Symptoms:
- SMTP conflicts
- Sync export errors

Resolution:
- Remove duplicate proxyAddress
- Re-run synchronization

---

## Cloud-only Account

Symptoms:
- User exists only in Microsoft Entra ID

Resolution:
- Decide whether to Fresh Provision, Soft Match, or Hard Match.

---

## Soft Match Failure

Possible Causes:
- UPN mismatch
- mail mismatch
- proxyAddresses mismatch

Resolution:
- Correct identity attributes
- Run Delta Sync

---

## Hard Match Required

Use when:
- Cloud mailbox already exists
- ImmutableID missing
- Soft Match unsuccessful

---

## ImmutableID Mismatch

Symptoms:
- Wrong AD object linked

Resolution:
- Verify ObjectGUID
- Recalculate Base64 ImmutableID
- Reapply using Microsoft Graph

---

## Delta Synchronization Issues

Checks:
- Scheduler status
- Connector space
- Synchronization Service Manager

---

## Export Errors

Review:
- Duplicate attributes
- Invalid UPN
- Invalid proxyAddresses

---

## Rollback Strategy

- Restore original UPN
- Restore mail/proxyAddresses
- Validate cloud identity
- Stop batch processing
