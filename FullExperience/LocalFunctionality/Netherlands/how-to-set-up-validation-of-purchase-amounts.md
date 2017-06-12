---
title: "How to: Set Up Validation of Purchase Amounts"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "purchase amounts, validating"
  - "purchase amounts, setting up"
ms.assetid: 653de2ad-9d89-4a62-8dc5-72af1202a306
caps.latest.revision: 18
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Set Up Validation of Purchase Amounts
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can activate the **Check Doc. Total Amounts** function to validate the total amount of purchase documents before posting a purchase invoice and purchase credit memo. By default, the purchase document total amount is validated when you post. The total amount of the inserted purchase lines must be equal to the amount including VAT and the VAT amount. To validate the purchase document amount automatically, you must enter the document amount including VAT and the document amount VAT on the **Purchase Invoice** or **Purchase Credit Memo** window.  
  
 If you have only one purchase line or several purchase lines with the same VAT percentage, the correct document amount VAT is calculated automatically when you insert the purchase lines and the document amount including VAT. If you have several purchase lines with different VAT percentages, the document amount VAT value must be changed manually.  
  
 You can also locate when the document total amounts and the total amounts of the inserted purchase lines are different. You can activate the **Show Totals on Purch. Inv.\/CM.** option to view the following in the inserted purchase lines:  
  
-   Total amount  
  
-   Total base amount  
  
-   Total VAT amount  
  
-   Total amount including VAT  
  
 The calculated amounts are displayed in the purchase invoice or purchase credit memo. By default, this total amount is not displayed.  
  
 You can activate this option only if the purchase invoice or purchase credit memo has:  
  
-   A minimum of one purchase line.  
  
-   The quantity field specified.  
  
### To set up validation of total amounts for purchase documents  
  
1.  In the **Search** box, enter **Purchases & Payables Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Show Totals on Purch. Inv.\/CM.**|Select to recalculate the totals on all purchase invoices and credit memos. This can take more time depending on the number of documents that must be recalculated.|  
    |**Check Doc. Total Amounts**|Select to modify the **Doc. Amount Incl. VAT** and **Doc. Amount VAT** fields on the **Purchase Invoice** and **Purchase Credit Memo** windows.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Purchases & Payables Setup](../../Purchasing/-$-n_460-purchases-payables-setup-$-.md)   
 [Netherlands Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/netherlands-local-functionality.md)