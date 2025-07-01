---
title: Set up validation of purchase amounts
description: You can validate the total amount on purchase invoices and credit memos before you post the documents.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords:
ms.date: 03/14/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Set up validation of purchase amounts

> [!NOTE]
> Businesses around the world can benefit from this functionality, so in 2025 release wave 1 we moved it out of the Dutch version and made it available to everyone.

You can validate the total amount on purchase invoices and credit memos before you post the documents. You can turn on the **Check Doc. Total Amounts** toggle on the **Purchases & Payables Setup** page. By default, [!INCLUDE [prod_short](includes/prod_short.md)] validates the total amount when you post the document. The total amount of the purchase lines must equal the amount including VAT and the VAT amount. To validate the amount automatically, you must enter the document amount including VAT and the document amount VAT on the **Purchase Invoice** or **Purchase Credit Memo** page.  

If you have only one purchase line, or several purchase lines with the same VAT percentage, the correct document amount VAT is calculated automatically when you add the purchase lines and the document amount including VAT. If you have several purchase lines with different VAT percentages, you must manually change the document amount VAT value.  

If the total amount on the document differs from the total amount of its lines, you can add a few values to the page that can help you find out why. You can add the total amount, total base amount, total VAT amount, and total amount including VAT values. The values display at the bottom of the document. To avoid clutter on the page during daily work, these values are hidden. To add these values to the document, turn on the **Show Totals on Purch. Inv.-CM.** toggle on the **Purchases & Payables Setup** page.  

You can turn on this option only if the purchase invoice or purchase credit memo has:  

- A minimum of one purchase line.  
- The quantity field specified.  

## To set up validation of total amounts for purchase documents  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
2. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show Totals on Purch. Inv./CM.**|Recalculate the totals on all purchase invoices and credit memos. Depending on how many documents you have, the recalculation can take some time.|  
    |**Check Doc. Total Amounts**|Verify the **Doc. Amount Incl. VAT** and **Doc. Amount VAT** fields on the purchase invoices and credit memos.|  

3. Choose the **OK** button.  

## Related information

[Check amounts on purchase invoices and credit memos](check-purchase-amounts.md)  
[Setting Up Purchases](sales-how-work-standard-lines.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]