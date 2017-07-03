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
# How to: Change Exchange Rates When You Post
You can change the exchange rate on existing journal lines or sales and purchase documents (blanket orders, orders, invoices, and credit memos) before posting. Before you can change exchange rates, you must set up currency codes and exchange rates.  
  
### To change an exchange rate when you post  
  
1.  Go to the document or journal you want to post and fill in the necessary fields.  
  
2.  To view the options, choose the **Currency Code** field on the relevant journal line or sales or purchase document.  
  
3.  Change the amount in either the **Exchange Rate Amount** field or the **Relational Exchange Rate Amount** field. The way in which you can change the exchange rate for each currency is defined by the option that you selected in the **Fix Exchange Rate Amount** field in the **Currency Exchange Rate** window. For Help about a specific field, select the field and press F1.  
  
4.  Choose the **OK** button in the **Change Exchange Rate** window. The exchange rate and the LCY amount for the specific sales or purchase document or journal line will be recalculated.  
  
 When you post, the amounts are converted to LCY according to the new exchange rate.  
  
## See Also  
 [About Using Additional Reporting Currencies](../about-using-additional-reporting-currencies.md)   
 [How to: Set Up the Additional Reporting Currency](../how-to-set-up-the-additional-reporting-currency.md)   
 [How to: Adjust Currency Exchange Rates](../how-to-adjust-currency-exchange-rates.md)