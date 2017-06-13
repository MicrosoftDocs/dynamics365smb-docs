---
title: "How to: Prepare VAT Entries for Posting"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting, VAT"
  - "VAT, posting"
ms.assetid: 961b8d9d-d9f9-4350-8094-b21121b99ca5
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Prepare VAT Entries for Posting
You may want to periodically remit the net VAT from sales and purchase transactions to the tax authorities. You can use the **VAT Settlement Worksheet** to prepare transactions with open VAT amounts for posting and copy the entries to the appropriate VAT settlement journal. This is typically done before you run the **Calc. and Post VAT Settlement** batch job to post and close VAT entries.  
  
### To prepare VAT entries for posting  
  
1.  In the **Search** box, enter **VAT Settlement Worksheet**, and then choose the related link.  
  
2.  Select the filters that define the VAT related transactions that you want to include in the VAT settlement.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Type**|Select the type of transactions that you want to include in the VAT settlement.|  
    |**View by**|Select the time period for the VAT settlement.|  
    |**View as**|Select how you want to view the net VAT. The options include **Net Change** and **Balance at Date**.|  
  
3.  Choose **Suggest Documents**. Transactions with open VAT entries that match the filters that you selected will be displayed.  
  
4.  Review the transactions that are included to ensure accuracy. If necessary, adjust your filter selection.  
  
5.  Choose **Copy Lines to Journal**.  
  
 The entries are copied to the appropriate VAT settlement journals. You can now run the **Calc. and Post VAT Settlement** batch job to close the VAT entries.  
  
## See Also  
 [Calc. and Post VAT Settlement](../Topic/\($%20B_20%20Calc.%20and%20Post%20VAT%20Settlement%20$\).md)   
 [About Setting Up VAT](../../Finance/about-setting-up-vat.md)   
 [How to: Set Up VAT Business Posting Groups](../../Finance/how-to-set-up-vat-business-posting-groups.md)   
 [How to: Assign VAT Business Posting Groups to Customer Accounts and Vendor Accounts](../../Finance/how-to-assign-vat-business-posting-groups-to-customer-accounts-and-vendor-accounts.md)   
 [How to: Correct VAT](../../Finance/how-to-correct-vat.md)   
 [VAT Entry](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32)