---
title: VAT settlement in Russia
description: Russian enhancements include VAT on purchase orders.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# VAT Settlement

It is possible to settlement full VAT or part of VAT.

## Setup

You must set up VAT posting groups in the **VAT posting setup** page. You can specify a VAT Business posting group and VAT product posting group.  

- Type of VAT calculation – normal VAT
- Type of transit VAT – Amount and tax
- You can specify a VAT transit account
- In the field "Type of unrealized VAT" - percentage
- Specify the VAT Account
- Checked the "VAT manual" installed
- The VAT settlement template and VAT settlement batch is specified  
- Specified Account Unreal. VAT

## VAT settlement

For manual settlement of VAT it is necessary to use the VAT settlement worksheet.   

The working date must be set to the current month in which VAT is to be settlement.  

> [!NOTE]
> Before calculating VAT, you must check the data of the VAT document. If you see that the data is empty, you must fill in the fields and use the -> Change Vendor VAT Invoices function.
> An additional way to change the VAT invoice data is to use this function in the vendor Ledger.

Click "Suggest documents" and get a list of documents to settlement VAT.  

Next, click on the "Copy lines to journal" button to transfer the lines (which are selected) to the VAT settlement journal.  

After posting the journal – formed transaction in the VAT register.

### VAT allocation

It is possible to consider only part of the amount of the VAT and write off the other part.

1. You must use the **VAT Allocation** function in the **VAT settlement Journal**.

2. Fill the fields:

- Type of VAT, you can select whether this allocation of VAT, write-off or charge.
- Account No. - account for VAT allocation.
- Specify the percentage or amount of the allocation.

3. Click OK. Post the journal.

## See Also

[Russia Local Functionality](russia-local-functionality.md)  
