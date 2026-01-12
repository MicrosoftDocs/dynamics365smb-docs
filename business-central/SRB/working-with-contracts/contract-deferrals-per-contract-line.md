---
title: Deferrals per contract line
description: Control deferral creation per contract line
author: TobiSIT
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8067_Primary, 
ms.date: 12/05/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Control Deferral Creation per Contract Line

Enable precise compliance with accounting standards by specifying, for each contract line, whether deferrals should be created when posting sales invoices. This feature provides granular control over revenue recognition and supports diverse contract scenarios.

## Overview

With subscription billing based on contracts, organizations often need to defer revenue for some contract lines but not others. This functionality allows users to determine, per contract line, whether deferrals are created, ensuring accurate financial reporting and flexibility for various contract types.

## Prerequisites

- Access to the Subscription Billing module.
- Appropriate permissions to configure contracts and subscription contract setup.
- Understanding of your organization’s revenue recognition policies.

## Key Concepts

- **Deferral:** The process of recognizing revenue over time, rather than immediately upon invoicing.
- **Contract Line:** An individual billing line within a customer or vendor contract, each of which can have its own deferral setting.

## How to Control Deferral Creation

### 1. Configuration Fields

Several fields and entities are involved in controlling deferral creation:

| Field Location                              | Field Name                   | Options / Default           | Description                                                                                  |
|----------------------------------------------|------------------------------|-----------------------------|----------------------------------------------------------------------------------------------|
| Subscription Contract Setup                  | Default Contract Deferrals    | Contract-dependent, Yes, No | Sets the default for new subscription package lines.                                         |
| Sub. Package Line Template                   | Contract Deferrals            | As above                    | Inherits from setup; sets default for new package lines.                                     |
| Subscription Package Line                    | Contract Deferrals            | As above                    | Inherits from template; can be overridden.                                                   |
| Sales Subscription Line                      | Contract Deferrals            | As above                    | Inherits from package line; not editable.                                                    |
| Subscription Line                            | Contract Deferrals            | As above                    | Inherits from sales subscription line or package line; determines if deferral is created.    |
| Subscription Contract Type                   | Default Create Contract Deferrals | Yes (default)           | Sets default for associated contracts.                                                       |
| Customer/Vendor Subscription Contract Header | Create Contract Deferrals     | Yes (default)               | Sets default for new (subscription) lines in the contract.                                     |

> **Note:** Changes to default settings only affect new contracts or contract lines. Existing contracts/lines must be updated manually if required.

### 2. Data Upgrade and Initialization

When upgrading or initializing the system:

- New fields are initialized according to their default values.
- For existing contracts and lines, deferral settings are set based on prior “Without Contract Deferrals” flags or contract assignment.
- Subscription lines with “Invoicing via Sales” are set to “No” for deferrals.
- Subscription lines with “Invoicing via Contract” inherit from the contract or setup.

### 3. Assigning Subscription Lines

- If a subscription line’s deferral setting is “Yes” or “No,” adding or removing it from a contract does not change its setting.
- If set to “Contract-dependent,” the setting updates based on the contract header’s value.

### 4. Creating Deferrals

Deferrals are always created per contract line, but only when the following conditions are met:
- The “Create Contract Deferrals” field in the contract header is set to “Yes, and
  - The “Create Contract Deferrals” field in the line is set to “Contract-dependent, or
- The “Create Contract Deferrals” field in the line is set to “Yes.

When posting a credit memo, only deferrals linked to the specific contract line are released.

### 5. Restrictions and Error Handling

Changing the deferral setting on a subscription line is only possible if there are no open (unreleased) deferrals for that line. If attempted, a corresponding error is displayed.

## Best Practices

- Set up default deferral preference in the Subscription Contract Setup to streamline contract ad subscription package creation.
- Review and adjust deferral defaults per contract type to set deferral creation in contracts more specifically.
- Review and adjust deferral settings for each subscription package as needed to ensure compliance with accounting standards.
- Regularly audit contract lines for correct deferral configuration, especially after upgrades or setup changes.

## Related Topics

- [Subscription Contract Setup](#)
- [Contract Deferrals](#)
- [subscription Packages](#)
