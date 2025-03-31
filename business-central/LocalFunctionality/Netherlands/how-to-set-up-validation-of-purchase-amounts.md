---
title: Set Up Validation of Purchase Amounts [NL]
description: Activate the **Check Doc. Total Amounts** function to ensure the total amount of purchase documents is validated before posting a purchase invoice or purchase credit memo.
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: Dutch version, Netherlands, purchase documents, purchase invoice, purchase credit memo, check document total amounts, validate purchase amounts
ms.date: 03/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up validation of purchase amounts in the Dutch version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can activate the **Check Doc. Total Amounts** function to validate the total amount of purchase documents before posting a purchase invoice and purchase credit memo. By default, the purchase document total amount is validated when you post. The total amount of the inserted purchase lines must be equal to the amount including VAT and the VAT amount. To validate the purchase document amount automatically, you must enter the document amount including VAT and the document amount VAT in the **Purchase Invoice** or **Purchase Credit Memo** page.  

If you have only one purchase line or several purchase lines with the same VAT percentage, the correct document amount VAT is calculated automatically when you insert the purchase lines and the document amount including VAT. If you have several purchase lines with different VAT percentages, the document amount VAT value must be changed manually.  

You can also locate when the document total amounts and the total amounts of the inserted purchase lines are different. You can activate the **Show Totals on Purch. Inv./CM.** option to view the following in the inserted purchase lines:  

- Total amount  
- Total base amount  
- Total VAT amount  
- Total amount including VAT  

The calculated amounts are displayed in the purchase invoice or purchase credit memo. By default, this total amount isn't displayed.  

You can activate this option only if the purchase invoice or purchase credit memo has:  

- A minimum of one purchase line.  
- The quantity field specified.  

## Set up validation of total amounts for purchase documents  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show Totals on Purch. Inv./CM.**|Select to recalculate the totals on all purchase invoices and credit memos. This can take more time depending on the number of documents that must be recalculated.|  
    |**Check Doc. Total Amounts**|Select to modify the **Doc. Amount Incl. VAT** and **Doc. Amount VAT** fields in the **Purchase Invoice** and **Purchase Credit Memo** pages.|  

1. Choose the **OK** button.  

## Related information

- [Netherlands Local Functionality](netherlands-local-functionality.md)  
- [Setting Up Purchases](../../sales-how-work-standard-lines.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
