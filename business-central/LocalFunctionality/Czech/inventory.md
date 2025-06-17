---
title: Czech Local Functionality - Inventory
description: This article outlines the features designed to enhance local inventory functionality in the Czech version of Business Central.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, CashDesk, Finance, CZ, Cash, Inventory
ms.date: 06/05/2025
ms.reviewer: v-soumramani
ms.author: v-makune
ms.service: dynamics-365-business-central
---

# Inventory in the Czech version

## Posting groups in transfer orders

Czech posting rules require location transfers to be posted with the defined Inventory Adjmt. Account different from other item Journal postings.
In the Transfer Orders functionality, fields for Gen. Bus. Post. Groups for Ship and Receive posting were added. This feature enables you to post different transfer orders with different General Posting Setup and also different from postings in item Journal.

In Transfer Route, fields for Gen. Bus. Post. Groups for Ship and Receive posting were added. This setup is automatically copied to transfer the order based on the used transfer route.

## Rounding account in inventory

The Rounding Account in the Inventory feature enables you to post all rounded costs (rounding entries in the Value Entry table) to another General Ledger Account instead of the Inventory Adjustment Account. This feature enables you to post a rounded cost on a different Account than the acquisition cost.

## Inventory – G/L reconciliation enhancements

According to the Czech specific requirements, the Inventory – G/L Reconciliation matrix form must into account take the Czech specific inventory posting Accounts: Inventory Rounding Account and Intermediate WIP Account. Since the Czech localized application contains modifications in the inventory posting, special Account for rounding functionalities, and special intermediate WIP accounts, must also be included in the Inventory – G/L Reconciliation matrix form.

These modifications have been introduced to the interface and the calculation procedures have been modified.

## Advanced features of the physical inventory

To comply with the legislation, companies require differentiation of accounting of deficits and surpluses. Thanks to the setting of default Whse. Net Change Template for these inventory movements in the Inventory Setup, the user can easily change Gen. Business Posting Group depending on the type of inventory movements.

Companies need to distinguish the posting of inventory movements of the same goods so they require line-break of physical inventory Journal line. Such accounting is required for legal reasons. For example, they need to have a different account for deficits in the limit, and another account for deficits over the limit.

## Inventory operations document

Users perform inventory operations such as: write down, reclassification and revaluation. They must have the possibility to print documents for these operations with the layout in compliance with the legal requirements.

Users also want to print a document for posted inventory operations.

For the reasons above, this feature provides the following reports:

- Inventory Movement Report is used to print documents from inventory Journals.
- Posted Inventory Document Report is used to print posted inventory operations.

## Inventory counting document

At the end of the period, users perform physical inventory counting to reconcile the actual (physical) value of inventory with the one registered in the system. At the end of the counting process, accounting department needs to archive final Inventory Counting Document containing posted values with names of company officials who under liability confirm with their signature that the quantities and amounts stated in the document correspond to ones physically present in company's inventory locations.

For the reasons above, this feature provides the following reports:

- Phys. Inventory List Report is used to print documents from Phys. Inventory Journals (existing report improved).
- Phys. Invt. Counting Document Report is used to print posted Phys. Inventory operations.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
