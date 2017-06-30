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
# How to: Adjust Currency Exchange Rates
There are no requirements for when or how often you should enter new exchange rates. Before you can update exchange rates, you must set up currency codes and currency exchange rates.  
  
### To update exchange rates  
  
1.  In the **Search** box, enter **Currencies**, and then choose the related link.  
  
2.  In the **Currencies** window, select the line with the currency code you want to update. On the **Actions** tab, choose **Exch. Rates**.  
  
3.  In the **Currency Exchange Rates** window that appears, fill in the fields on the next blank line.   
  
4.  Close the windows.  
  
5.  Run the **Adjust Exchange Rates** batch job to adjust the exchange rates of posted customer, vendor and bank account entries. The batch job also updates additional reporting currency amounts on general ledger entries.  
  
## See Also  
 Adjust Exchange Rates   
 [About Using Additional Reporting Currencies](../about-using-additional-reporting-currencies.md)   
 [How to: Change Exchange Rates When You Post](../how-to-change-exchange-rates-when-you-post.md)