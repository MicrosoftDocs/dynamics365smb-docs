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
# About Using Additional Reporting Currencies
As companies operate in increasingly more countries\/regions, it becomes more important that they be able to review or report financials in more than one currency. The program supports use of multiple currencies. Within the program, your general ledger is set up using your local currency \(LCY\), and another currency is set up as an additional currency, with a current exchange rate assigned.  
  
 By designating a second currency as an Additional Reporting Currency, "[!INCLUDE[d365fin](../../includes/d365fin_md.md)] will automatically record amounts in both LCY and this additional reporting currency on each G\/L entry and on other entries, such as VAT entries. When the program calculates G\/L entry amounts in an additional reporting currency, the program uses the information from the **Currency Exchange Rates** window to find the relevant exchange rate.  
  
> [!WARNING]  
>  The Additional Reporting Currency functionality should NOT be used as a basis for financial statement translation. It is not a tool that can perform translation of foreign subsidiary financial statements as part of a company consolidation. The additional reporting currency functionality only provides the option of preparing reports in another currency, as if that currency was the company’s local currency.  
  
## Adjusting Exchange Rates  
 Because exchange rates fluctuate constantly, additional currency equivalents in your system must be adjusted periodically. If these adjustments are not done, amounts that have been converted from foreign \(or additional\) currencies and posted to the general ledger in LCY may be misleading. In addition, daily entries posted before a daily exchange rate is entered into the program must be updated after the daily exchange rate information is entered. The Adjust Exchange Rates batch job is used to adjust the exchange rates of posted customer, vendor and bank account entries. It can also update additional reporting currency amounts on G\/L entries.  
  
## Displaying Reports and Amounts in the Additional Reporting Currency  
 Using an additional reporting currency can assist the reporting process for a company in the following cases:  
  
-   Companies in non-EU countries\/regions that have a high proportion of transactions with EU country\/region companies. In this case, the non-EU company may also wish to report in euro to make its financial reports more usable for its EU trade partners.  
  
-   Companies that also wish to display reports in a more internationally traded currency than their own local currency.  
  
 Several reports in the General Ledger application area are based on G\/L entries. To display the financial data in the report in the additional reporting currency, you simply place a check mark in the Show in Add.-Currency field on the Options FastTab for the relevant G\/L report.  
  
## See Also  
 Adjust Add. Reporting Currency   
 [How to: Set Up the Additional Reporting Currency](../how-to-set-up-the-additional-reporting-currency.md)   
 [How to: Adjust Currency Exchange Rates](../how-to-adjust-currency-exchange-rates.md)   
 [How to: Set Up the Additional Reporting Currency](../how-to-set-up-the-additional-reporting-currency.md)