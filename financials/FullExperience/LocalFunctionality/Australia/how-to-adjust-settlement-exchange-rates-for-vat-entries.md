---
title: "How to: Adjust Settlement Exchange Rates for VAT Entries"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT settlement"
  - "VAT, adjusting settlement exchange rates"
  - "VAT, exchange rates"
  - "adjusting, exchange rates for VAT"
ms.assetid: b594b19c-5ba8-4422-8bf5-cfe0787e5b82
caps.latest.revision: 18
ms.author: "edupont"
translation.priority.ht: 
  - "en-au"
---
# How to: Adjust Settlement Exchange Rates for VAT Entries
You can use the **Adjust Settlement Exch. Rates** batch job to settle VAT entries according to the government exchange rate as defined in the **Currency Exchange Rate** table.  
  
### To adjust settlement exchange rates for VAT  
  
1.  In the **Search** box, enter **Adjust Settlement Exch. Rates**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_28140\_N\_2\_1340012 Settlement Period $\)**|Specifies the start date of the settlement period.|  
    |**\($ B\_28140\_N\_2\_1340010 Ending Date $\)**|Specifies the end date of the settlement period.|  
    |**\($ B\_28140\_N\_2\_1340008 Posting Description $\)**|Specifies the posting description.|  
    |**\($ B\_28140\_N\_2\_1340002 Document No. $\)**|Specifies the document number for which you want to settle VAT entries.|  
    |**\($ B\_28140\_N\_2\_1340004 Posting Date $\)**|Specifies the posting date of the document.|  
    |**\($ B\_28140\_N\_2\_1340000 Use Daily Settlement Exch. Rate $\)**|Select if you want to use the daily settlement exchange rate.|  
  
3.  Choose the **OK** button.  
  
     The VAT entries are adjusted and you can view them in the **VAT Register** report.  
  
## See Also  
 Currency Exchange Rate Table   
 VAT Entries   
 VAT Register   
 Exch. Rate Adjmt. Reg.