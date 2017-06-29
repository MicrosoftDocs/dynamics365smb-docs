---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Adjust Settlement Exchange Rates for VAT Entries
You can use the **Adjust Settlement Exch. Rates** batch job to settle VAT entries according to the government exchange rate as defined in the **Currency Exchange Rate** table.  
  
### To adjust settlement exchange rates for VAT  
  
1.  In the **Search** box, enter **Adjust Settlement Exch. Rates**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
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