---
title: 'How to: Suggest Vendor Payments| Microsoft Docs'
description: 'How to: Suggest Vendor Payments'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sgroespe

---
# How to: Suggest Vendor Payments
In the **Payment Journal** window, you can use the **Suggest Vendor Payments** batch job to suggest payment lines. Lines for things like payments that are due soon, or payments where a payment discount is available, are suggested based on your settings.

To benefit fully from suggested lines, you must first prioritize your vendors. For more information, see [How to: Prioritize Vendors](purchasing-how-prioritize-vendors.md).  

Vendor entries that are not **On Hold** are not included.  

**Important:** If you want to take advantage of payment discounts, and have entered an available amount, the amount will be used for:  

* Prioritized overdue vendor entries first in order of priority.  
* Overdue vendor entries that are not prioritized.  
* Open vendor entries that qualify for payment discounts, arranged by vendor number.  

## To use the Suggest Vendor Payments function
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Payment Journals**, and then choose the related link.  
2. Open the relevant journal, and then choose the **Suggest Vendor Payments** action.  
3. Fill in the fields as necessary. Choose a field to read a short description of the field or link to more information.  
4. Choose the **OK** button.  

## To insert the due date as posting date on payment journal lines
When you use the **Suggest Vendor Payments** batch job to create payment lines for your vendors, you can fill two special fields to make sure that the generated lines use the due date to calculate the posting date. These fields are **Calculate Posting Date from Applies-to-Doc Due Date** and **Applies-to-Doc Due Date Offset**.  

**Important:** You cannot use the **Calculate Posting Date from Applies-to-Doc Due Date** field together with the **Find Payment Discounts** field or the **Summarize per Vendor** field. If the posting date is based on the due date, some payment discounts may not calculate correctly because the posting date is after the payment discount date.  

Also, if the calculated posting date is in the past, then the posting date is moved up to the work date, and a warning is displayed.  

Alternatively, you can manually create payment lines using the due date to calculate the posting date. After you apply vendor ledger entries, you can use the **Calculate Posting Date** action to update the posting date on the journal line with the due date of the related purchase invoice. For more information, see [How to: Apply Purchase Transactions Manually](payables-how-apply-purchase-transactions-manually.md).  

**Note:** If the purchase invoice is overdue, the posting date is set to the work date, and the font on the line becomes red.  

## See Also
[Managing Payables](payables-manage-payables.md)  
[Make Payments](payables-make-payments.md)  
[Working With General Journals](ui-work-general-journals.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

