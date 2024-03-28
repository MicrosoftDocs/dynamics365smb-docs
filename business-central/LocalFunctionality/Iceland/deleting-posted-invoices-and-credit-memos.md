---
title: Deleting posted invoices and credit memos [IS]
description: In Iceland, in accordance with legislation, you can't delete posted sales and purchase invoices and credit memos.
services: project-madeira 
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: Iceland, post, invoice, credit memo
ms.date: 12/11/2023
ms.author: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Delete posted invoices and credit memos in the Icelandic version

## Before v24.0 

In Iceland, in accordance with legislation, you can't delete sales and purchase invoices and credit memos after they're posted. In [!INCLUDE[prod_short](../../includes/prod_short.md)], the **Delete** command isn't available for these types of posted documents. 

## After v24.0

If you activated new [Icelandic localization based on W1 Base App](iceland-global-core-app.md), you can delete sales and purchase invoices and credit memos, but only in a case they are older then 7 years after begining of new fiscal year. 

> [!NOTE]
> Technically this is controled with the new ENUM field **Document Retention Period** in the **General Ledger Setup** page. This field is hidden and has the **IS Docs Retention Period** option by default enabling this control.

## See also  

[Invoice Sales](../../sales-how-invoice-sales.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
