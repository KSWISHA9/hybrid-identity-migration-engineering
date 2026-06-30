# Hard Match Workflow

## Purpose

Describes the controlled process used to merge an existing cloud-only Microsoft Entra ID account with its corresponding on-premises Active Directory account.

## Workflow

1. Validate production cloud account
2. Identify duplicate synchronized account
3. Convert AD ObjectGUID to ImmutableID
4. Assign ImmutableID with Microsoft Graph
5. Run Delta Synchronization
6. Validate final hybrid identity

## Validation

- AccountEnabled = True
- OnPremisesSyncEnabled = True
- ImmutableID assigned
- License preserved
- Mailbox preserved
- Duplicate removed

## Lessons Learned

Perform pilot migrations before batch processing and stop immediately if any safety validation fails.
