---
title: Create an advance letter 
description: This article describes how to manually create an advance invoice using Advance Payments in the Czech version.  
author: v-pejano  
ms.reviewer: v-pejano  
ms.author: v-pejano  
ms.service: dynamics-365-business-central  
ms.topic: how-to  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 09/17/2025
ms.custom: bap-template  

---

# Create an advance letter

To create an advance letter manually, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters** or **Purchase Advance Letters**, and then select the related link.
2. In the list, create a new document by selecting the **New** action.
3. Select the **Advance Letter Template**, which defines the number series, VAT handling, posting behavior, and other settings.
4. Confirm the **No.** field to assign a document number from the selected number series.  
5. In the header, assign the **Bill-to Name**.
6. In the invoice lines, enter the **VAT Prod. Posting Group** and the **Amount Including VAT**.
7. The default status of an advance invoice is **New**, meaning you can edit it but it can't be paid or used in a final invoice.  
8. Use the **Release** action to change the status to **To Pay**. The invoice becomes payable.

   > [!NOTE]
   > Releasing the document creates an **Initial Entry** in the advance entries, with the posting date from the document’s posting date and the full advance amount.  
   >
   > This initial entry doesn't affect accounting. It just tracks the remaining amount available for payment.

9. You can print the advance invoice using the **Report – Advance Letter** action, or generate a PDF attachment using the **Report – Attach as PDF** action.
10. If you need to modify the advance letter, you can reopen it using the **Reopen** action. This sets the status back to **New** and allows editing. A negative **Initial Entry** is automatically created to reverse the previous entry.
11. In the **FactBox** on the letter page, you can monitor the current advance amount, the remaining amount to be paid, the remaining amount available to be used, and the VAT base and VAT amount.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
