---
title: Creating an Advance Letter 
description: This section describes how to manually create an advance invoice using the Czech Advance Payments Localization extension in Business Central.  
author: v-pejano  

ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 10/01/2021  
ms.reviewer: v-pejano  
ms.author: v-pejano  
---

# Creating an Advance Letter

To create an advance letter manually, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link. For purchases, search for **Purchase Advance Letters**.
2. In the list, create a new document by selecting the **New** action.
3. Select the **Advance Letter Template**, which defines the number series, VAT handling, posting behavior, and other settings.
4. Confirm the **No.** field to assign a document number from the selected number series.  
   The advance letter is now created.
5. In the header, assign the **Bill-to Name**.
6. In the invoice lines, enter the **VAT Prod. Posting Group** and the **Amount Including VAT**.
7. The default status of an advance invoice is **New**, meaning it can still be edited but cannot be paid or used in a final invoice.  
   Use the **Release** action to change the status to **To Pay**.  
   The invoice becomes payable.

   Releasing the document creates an **Initial Entry** in the advance entries, with the posting date taken from the document’s posting date and the full advance amount.  
   This initial entry has no accounting impact; it is used solely to track the remaining amount available for payment.

8. You can print the advance invoice using the **Report – Advance Letter** action, or generate a PDF attachment using the **Report – Attach as PDF** action.
9. If you need to modify the advance letter, you can reopen it using the **Reopen** action. This sets the status back to **New** and allows editing.  
   A negative **Initial Entry** is automatically created to reverse the previous entry.
10. In the **FactBox** on the letter page, you can monitor the current advance amount, the remaining amount to be paid, the remaining amount available to be used, and the VAT base and VAT amount.

## See Also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
