---
title: Pay an advance letter  
description: This article describes how to pay an advance letter using Advance Payments in the Czech version.  
author: v-pejano  
ms.reviewer: v-pejano  
ms.author: v-pejano  
ms.service: dynamics-365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 09/17/2025  
ms.custom: bap-template
---

# Pay an advance letter

If an advance letter has the status **To Pay**, it can be paid either via a general journal or a cash receipt.

## Pay an advance letter via a general journal

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then select the related link.
2. Select a general journal template.
3. To pay the advance letter, on the journal line, in the **Document Type** field, choose **Payment**.
4. Depending on the type of advance letter (sales/purchase), enter the **Customer No.** or **Vendor No.**.
5. In the **Advance Letter No.** field on the journal line, a list of all unpaid or partially paid advance letters is available. The list is filtered on the currency code selected on the journal line. Select the advance letter you want to pay and confirm your selection. You can reduce the proposed amount if you want to make a partial payment.  

   > [!NOTE]
   > You can only link one advance letter per journal line. To pay multiple advance letters, use multiple journal lines.

6. After you post the journal, [!INCLUDE [prod_short](../../includes/prod_short.md)] creates a line where the **Entry Type** field contains **Payment** in the advance ledger entries.

## Pay an advance letter via a cash document

The steps to pay an advance letter using a cash document are similar to the steps for a general journal.

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Documents**, and then select the related link.
2. Create a new cash document.
3. Depending on the type of advance letter (sales/purchase), enter the appropriate **CustomerNo.** or **Vendor No.**.
4. In the **Advance Letter No.** field on the cash receipt line, a list of all unpaid or partially paid advance letters is available, filtered by the cash receipt’s currency code. Select the advance letter you want to pay and confirm your selection. You can reduce the proposed amount if you want to make a partial payment.  

   > [!NOTE]
   > You can only link one advance letter per cash receipt line. To pay multiple advance invoices, use multiple lines.

5. After you post the cash receipt, [!INCLUDE [prod_short](../../includes/prod_short.md)] creates a line where the **Entry Type** field contains **Payment** in the advance ledger entries.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
