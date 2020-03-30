---
title: How to Set Up Validation of Purchase Amounts
description: In Business Central, you can activate the Check Doc. Total Amounts function to validate the total amount of purchase documents before posting a purchase invoice and purchase credit memo.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up Validation of Purchase Amounts
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can activate the **Check Doc. Total Amounts** function to validate the total amount of purchase documents before posting a purchase invoice and purchase credit memo. By default, the purchase document total amount is validated when you post. The total amount of the inserted purchase lines must be equal to the amount including VAT and the VAT amount. To validate the purchase document amount automatically, you must enter the document amount including VAT and the document amount VAT in the **Purchase Invoice** or **Purchase Credit Memo** page.  

If you have only one purchase line or several purchase lines with the same VAT percentage, the correct document amount VAT is calculated automatically when you insert the purchase lines and the document amount including VAT. If you have several purchase lines with different VAT percentages, the document amount VAT value must be changed manually.  

You can also locate when the document total amounts and the total amounts of the inserted purchase lines are different. You can activate the **Show Totals on Purch. Inv./CM.** option to view the following in the inserted purchase lines:  

- Total amount  
- Total base amount  
- Total VAT amount  
- Total amount including VAT  

The calculated amounts are displayed in the purchase invoice or purchase credit memo. By default, this total amount is not displayed.  

You can activate this option only if the purchase invoice or purchase credit memo has:  

- A minimum of one purchase line.  
- The quantity field specified.  

## To set up validation of total amounts for purchase documents  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
2.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show Totals on Purch. Inv./CM.**|Select to recalculate the totals on all purchase invoices and credit memos. This can take more time depending on the number of documents that must be recalculated.|  
    |**Check Doc. Total Amounts**|Select to modify the **Doc. Amount Incl. VAT** and **Doc. Amount VAT** fields in the **Purchase Invoice** and **Purchase Credit Memo** pages.|  

3.  Choose the **OK** button.  

## See Also  
[Netherlands Local Functionality](netherlands-local-functionality.md)  
[Setting Up Purchases](../../sales-how-work-standard-lines.md)
