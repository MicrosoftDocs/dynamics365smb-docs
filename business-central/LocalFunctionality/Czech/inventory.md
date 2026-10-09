---
title: Czech Local Functionality - Inventory
description: This article outlines the features designed to enhance local inventory functionality in the Czech version of Business Central.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, CashDesk, Finance, CZ, Cash, Inventory
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Inventory in the Czech version

## Posting groups in transfer orders

Czech posting rules require location transfers to post with an **Inventory Adjmt. Account** that's different from other item journal postings.
The transfer order functionality includes **Gen. Bus. Post. Group Ship** and **Gen. Bus. Post. Group Receive** fields, so you can post transfer orders with a different general posting setup than the one used for item journal postings.

The **Transfer Route** page also includes **Gen. Bus. Post. Group Ship** and **Gen. Bus. Post. Group Receive** fields. This setup is automatically copied to a transfer order based on the transfer route it uses.

## Rounding account in inventory

The rounding account in inventory feature lets you post all rounded costs (rounding entries in the `Value Entry` table) to a general ledger account other than the inventory adjustment account. To set it up, enter an account in the **Invt. Rounding Adj. Account** field on the **General Posting Setup** page. This feature lets you post a rounded cost to a different account than the acquisition cost.

## Inventory – G/L reconciliation enhancements

Because the Czech-localized application adds its own inventory posting accounts, the **Inventory – G/L Reconciliation** matrix must also take these Czech-specific accounts into account: the inventory rounding account and the intermediate WIP account.

These additions are reflected both in the user interface and in the underlying calculation procedures.

## Advanced features of the physical inventory

To comply with legislation, companies need to account for deficits and surpluses separately. On the **Inventory Setup** page, you can set a default inventory movement template for positive and negative physical inventory adjustments. Each template can specify its own **Gen. Bus. Posting Group**, so you can change the posting group depending on the type of inventory movement.

Companies also need to distinguish between postings for the same item, for example to use a different account for a deficit within a defined limit than for a deficit that exceeds it. To support this, each line on a physical inventory counting document can be assigned its own inventory movement template, which determines the **Gen. Bus. Posting Group** used for that line.

## Inventory operations document

Users perform inventory operations such as write-down, reclassification, and revaluation. They need to print documents for these operations with a layout that complies with legal requirements, and they also need to print a document for posted inventory operations.

For these reasons, this feature provides the following reports:

- **Inventory Document** prints documents from inventory journals.
- **Posted Inventory Document** prints posted inventory operations.

## Inventory counting document

At the end of a period, users perform physical inventory counting to reconcile the actual (physical) value of inventory with the value registered in the system. At the end of the counting process, the accounting department needs to archive a final inventory counting document that contains the posted values along with the names of company officials who, under liability, confirm with their signature that the quantities and amounts in the document match what's physically present in the company's inventory locations.

For these reasons, this feature provides the **Physical Inventory Counting Document** report, which prints the signed document for posted physical inventory counts.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
