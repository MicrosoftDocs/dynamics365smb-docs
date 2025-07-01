---
title: Advance Letter Payment  
description: This section describes how to pay an advance letter using the Czech Advance Payments Localization extension in Business Central.  
author: v-pejano  

ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 10/01/2021  
ms.reviewer: v-pejano  
ms.author: v-pejano  
---

# Paying an Advance Letter

If an advance letter has the status **To Pay**, it can be paid either via a general journal or a cash receipt.

## Paying an Advance Letter via General Journal

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then select the related link.
2. Select a general journal template.
3. To pay the advance letter, set **Document Type = Payment** on the journal line.
4. Enter the appropriate **Customer/Vendor No.** depending on the type of advance letter (sales/purchase).
5. In the **Advance Letter No.** field on the journal line, a list of all unpaid or partially paid advance letters is available. The list is filtered by the currency code selected on the journal line.  
   Select the advance letter you want to pay and confirm your selection. You can reduce the proposed amount if you want to make a partial payment.  
   You can only link one advance letter per journal line. To pay multiple advance letters, use multiple journal lines.
6. After posting the journal, a line with **Entry Type = Payment** is created in the advance ledger entries.

## Paying an Advance Letter via Cash Document

When paying an advance letter using a cash document, follow similar steps as for the general journal:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Documents**, and then select the related link.
2. Create a new cash document.
3. Enter the appropriate **Customer/Vendor No.** depending on the type of advance letter (sales/purchase).
4. In the **Advance Letter No.** field on the cash receipt line, a list of all unpaid or partially paid advance letters is available, filtered by the cash receipt’s currency code.  
   Select the advance letter you want to pay and confirm your selection. You can reduce the proposed amount if you want to make a partial payment.  
   You can only link one advance letter per cash receipt line. To pay multiple advance invoices, use multiple lines.
5. After posting the cash receipt, a line with **Entry Type = Payment** is created in the advance ledger entries.

## See Also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
