# Two-Object Pattern

## Purpose

This document explains the two-object identity problem commonly seen during Microsoft 365 and hybrid identity migrations.

## Business Scenario

OmniVerse Enterprises acquired another organization where Microsoft 365 accounts were created before Active Directory synchronization was standardized.

This created two separate identities for some users:

1. A cloud-only production account
2. A synchronized duplicate account

## The Problem

The cloud-only account contained the user's real business data:

- Mailbox
- License
- Teams data
- OneDrive data
- Existing sign-in history

The synchronized duplicate account was created later by Microsoft Entra Connect and represented the on-premises Active Directory object.

This caused identity conflicts and prevented a clean hybrid identity state.

## Two-Object Pattern

```text
Cloud-only production account
Licensed / mailbox exists / no ImmutableID

+

Synced duplicate account
No license / synced from AD / has ImmutableID
```

## Target State

The final goal is one clean hybrid identity:

```text
One Microsoft Entra user
Licensed
Mailbox preserved
Synced from Active Directory
ImmutableID assigned
No duplicate object
```

## Engineering Risk

The biggest risk is accidentally deleting or overwriting the production cloud account that contains the user's mailbox and license.

For that reason, migration steps must include safety checks before purging duplicates or assigning ImmutableID values.

## Safety Checks

Before any hard match:

- Confirm the production cloud account exists
- Confirm the production account is licensed
- Confirm the duplicate synced object is identified
- Confirm the correct AD ObjectGUID
- Confirm the correct ImmutableID value
- Confirm the production account still exists before purging anything
- Log every action

## Lessons Learned

The two-object pattern is one of the most important problems in hybrid identity migrations.

A successful migration depends on identifying which object owns the data, which object owns the synchronization link, and how to safely merge them into one identity.
