---
title: VAT settlement in Russia
description: Learn about VAT settlement in Russia, including setup, manual settlement, and VAT allocation features in Business Central.
author: DianaMalina
ms.topic: article
ms.search.keywords: VAT, VAT settlement, VAT allocation, VAT posting setup, VAT settlement worksheet, Russia
ms.date: 07/21/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# VAT settlement

It's possible to settlement full VAT or part of VAT.

## Setup

You must set up VAT posting groups in the **VAT posting setup** page. You can specify a VAT Business posting group and VAT product posting group.  

- Type of VAT calculation – normal VAT
- Type of transit VAT – Amount and tax
- You can specify a VAT transit account
- In the field "Type of unrealized VAT" - percentage
- Specify the VAT Account
- Checked the "VAT manual" installed
- The VAT settlement template and VAT settlement batch are specified  
- Specified Account Unreal. VAT

## VAT manual settlement

For manual settlement of VAT it's necessary to use the VAT settlement worksheet.

The working date must be set to the current month in which VAT is to be settlement.  

> [!NOTE]
> Before calculating VAT, you must check the data of the VAT document. If you see that the data is empty, you must fill in the fields and use the -> Change Vendor VAT Invoices function.
> An additional way to change the VAT invoice data is to use this function in the vendor Ledger.

Select **Suggest documents** and get a list of documents to settlement VAT.  

Next, select the **Copy lines to journal** button to transfer the lines (which are selected) to the VAT settlement journal.  

After posting the journal – formed transaction in the VAT register.

### VAT allocation

It's possible to consider only part of the amount of the VAT and write off the other part.

1. You must use the **VAT Allocation** function in the **VAT settlement Journal**.
1. Fill the fields:

   - Type of VAT, you can select whether this allocation of VAT, write-off, or charge.
   - Account No. - account for VAT allocation.
   - Specify the percentage or amount of the allocation.

1. Select **OK**. Post the journal.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
