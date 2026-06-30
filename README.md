# Enterprise Identity Migration & Synchronization Operations (IAM-002)

> OmniVerse Enterprise Engineering Portfolio

## Overview

This project documents an enterprise identity migration scenario involving cloud-only Microsoft Entra ID accounts, synchronized Active Directory accounts, UPN migration, Soft Match, Hard Match, ImmutableID, Microsoft Graph automation, and validation.

IAM-002 builds directly on IAM-001 by using the hybrid identity platform created with Microsoft Entra Connect.

## Business Scenario

OmniVerse Enterprises recently acquired another organization. The acquired company already had Microsoft 365 cloud-only accounts created before Active Directory synchronization was standardized.

The objective is to merge cloud-only accounts with synchronized Active Directory identities without losing mailboxes, licenses, Teams data, OneDrive data, or creating duplicate identities.

## Project Phases

1. Discovery and Identity Audit
2. Cloud-only vs Synced Identity Classification
3. UPN Migration
4. Soft Match
5. Hard Match
6. ImmutableID Assignment
7. Microsoft Graph Automation
8. Batch Migration
9. Validation and Rollback

## Skills Demonstrated

- Microsoft Entra ID
- Active Directory
- Microsoft Entra Connect
- Microsoft Graph PowerShell
- Soft Match
- Hard Match
- ImmutableID
- UPN Migration
- Duplicate Attribute Troubleshooting
- Batch Automation
- Enterprise Identity Migration
- Safety Checks and Rollback Planning

## Created By

Keshawn Lynch
