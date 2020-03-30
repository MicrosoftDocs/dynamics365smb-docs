---
title: Czech Local Functionality - Inventory | Microsoft Docs
description: This section describes local functionality - Inventory
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, CashDesk, Finance, CZ, Cash, Inventory
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-makune
---

# Inventory

## Posting Groups in Transfer Orders
Czech posting rules require location transfers to be posted with the defined Inventory Adjmt. Account different from other item Journal postings.
In the Transfer Orders functionality, fields for Gen. Bus. Post. Groups for Ship and Receive posting were added. This feature enables you to post different transfer orders with different General Posting Setup and also different from postings in item Journal.

In Transfer Route, fields for Gen. Bus. Post. Groups for Ship and Receive posting were added. This setup is automatically copied to transfer the order based on the used transfer route.

## Rounding Account in Inventory
The Rounding Account in the Inventory feature enables you to post all rounded costs (rounding entries in the Value Entry table) to another General Ledger Account instead of the Inventory Adjustment Account. This feature enables you to post a rounded cost on a different Account than the acquisition cost.

## Inventory – G/L Reconciliation Enhancements
According to the Czech specific requirements, the Inventory – G/L Reconciliation matrix form must into account take the Czech specific inventory posting Accounts: Inventory Rounding Account and Intermediate WIP Account. Since the Czech localized application contains modifications in the inventory posting, special Account for rounding functionalities, and special intermediate WIP accounts, must also be included in the Inventory – G/L Reconciliation matrix form.

These modifications have been introduced to the interface and the calculation procedures have been modified.

## Advanced Features of the Physical Inventory
To comply with the legislation, companies require differentiation of accounting of deficits and surpluses. Thanks to the setting of default Whse. Net Change Template for these inventory movements in the Inventory Setup, the user can easily change Gen. Business Posting Group depending on the type of inventory movements.

Companies need to distinguish the posting of inventory movements of the same goods so they require line-break of physical inventory Journal line. Such accounting is required for legal reasons. For example, they need to have a different account for deficits in the limit, and another account for deficits over the limit.

## Inventory Operations Document
Users perform inventory operations such as: write down, reclassification and revaluation. They must have the possibility to print documents for these operations with the layout in compliance with the legal requirements.

Users also want to print a document for posted inventory operations.

For the reasons above, this feature provides the following reports:

- Inventory Movement Report is used to print documents from inventory Journals.
- Posted Inventory Document Report is used to print posted inventory operations.

## Inventory Counting Document
At the end of the period, users perform physical inventory counting to reconcile the actual (physical) value of inventory with the one registered in the system. At the end of the counting process, accounting department needs to archive final Inventory Counting Document containing posted values with names of company officials who under liability confirm with their signature that the quantities and amounts stated in the document correspond to ones physically present in company’s inventory locations.

For the reasons above, this feature provides the following reports:

- Phys. Inventory List Report is used to print documents from Phys. Inventory Journals (existing report improved).
- Phys. Invt. Counting Document Report is used to print posted Phys. Inventory operations.

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)
