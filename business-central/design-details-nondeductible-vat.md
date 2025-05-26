---
title: Design details - Non-deductible VAT
description: This article provides information about non-deductible value-added tax (VAT) that's payable by a purchaser, but that isn't deductible from the purchaser's own VAT liability.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 07/04/2023
ms.author: altotovi

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Design details: Non-deductible VAT

Non-deductible value-added tax (VAT) is the VAT that's payable by a purchaser, but that isn't deductible from the purchaser's own VAT liability. Because it can be difficult to know where and how an item is used, you must contact the local tax authorities in your country or region to determine whether a specified percentage of the VAT is deductible. Even when you know that a specific percentage of the VAT isn't deductible, there are different models for handling non-deductible amounts as they are related to **items** and **fixed assets**.

## Prerequisites for using non-deductible VAT

To use and post non-deductible VAT, follow these steps.

1. On the **VAT Setup** page, select **Enable Non-Deductible VAT** to enable the feature.
2. On the **VAT Posting Setup** page, select which VAT posting groups can use non-deductible VAT.

## Examples

For the following examples, non-deductible VAT is enabled, and the following setup is completed:

- The **VAT Product Posting Group** field is set to **NDVAT**.
- On the **VAT Posting Setup** page:

    - **NDVAT** is set as the VAT product posting group, and **DOMESTIC** is set as the VAT business posting group.
    - The **VAT Identifier** value must be unique.
    - The **VAT %** field is set to **25**.
    - The **Allow Non-deductible VAT** field is set to **Allow**.
    - The **Non-deductible VAT %** field is set to **100**.
    - The **VAT Calculation Type** field is set to **Normal VAT**.
    - Only the sales VAT account and purchase VAT account are configured.

All the examples use items and fixed assets where the VAT product posting group is **NDVAT**.

### Items

A new item has **NDVAT** set as the VAT product posting group. In the purchase document, **Quantity** = **1** and **Direct Unit Cost Excl. VAT** = **1,000.00**.

Regardless of the option that's used, the results in the **VAT entry** are the same.

| Document Type | Type | Base | Amount | Non-Deductible VAT Base | Non-deductible VAT Amount |
|---|---|---|---|---|---|
| Invoice | Purchase | 0.00 | 0.00 | 1,000.00 | 250.00 |

The details are shown in the **Value Entries**.

> [!NOTE]
> You can enable the **Use for Item Cost** field on the **VAT Setup** page.

#### Use for Item Cost isn't enabled

| Item Ledger Entry Type | Entry Type | Cost Amount (Actual) | Item Ledger Entry Quantity |
|---|---|---|---|
| Purchase | Direct Cost | 1,000.00 | 1 |

#### Use for Item Cost is enabled

| Item Ledger Entry Type | Entry Type | Cost Amount (Actual) | Item Ledger Entry Quantity |
|---|---|---|---|
| Purchase | Direct Cost | 1,250.00 | 1 |

### Fixed assets

A new fixed asset has the acquisition cost account set to use **NDVAT** as the VAT product posting group. In the purchase document, **Quantity** = **1** and **Direct Unit Cost Excl. VAT** = **1,000.00**.

Regardless of the option that's used, the results in the **VAT entry** are the same.

| Document Type | Type | Base | Amount | Non-Deductible VAT Base | Non-deductible VAT Amount |
|---|---|---|---|---|---|
| Invoice | Purchase | 0.00 | 0.00 | 1,000.00 | 250.00 |

The details are shown in the **Fixed Asset Ledger Entries**.

> [!NOTE]
> You can enable the **Use for Fixed Asset Cost** field on the **VAT Setup** page.

#### Use for Fixed Asset Cost isn't enabled

| Document Type | FA Posting Type | Amount | VAT Amount |
|---|---|---|---|
| Invoice | Acquisition Cost | 1,000.00 | 250.00 |

#### Use for Fixed Asset Cost is enabled

| Document Type | FA Posting Type | Amount | VAT Amount |
|---|---|---|---|
| Invoice | Acquisition Cost | 1,000.00 | 250.00 |
| Invoice | Acquisition Cost | 250.00 | 0.00 |

## Related information

[Set up non-deductible VAT](finance-setup-nondeductible-vat.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
