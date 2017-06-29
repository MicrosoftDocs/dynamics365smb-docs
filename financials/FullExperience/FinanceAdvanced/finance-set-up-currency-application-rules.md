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
# Set Up Currency Application Rules
You can allow transactions in different currencies to be applied to one another, for example, if you record a purchase order in one currency and then make the corresponding payment in a different currency. You can:  
  
-   Allow all currencies to be applied to one another,  
  
-   Prohibit applying any currencies to one another, or  
  
-   Specify a group of Economic and Monetary Union \(EMU\) currencies that can be applied to one another.  
  
 When you apply entries in different currencies to each other, there may be a difference between the two amounts when they are converted to LCY. You can specify how large of a difference you will allow, so that the entries can be closed. The difference will then be posted as a rounding difference.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Allow payments in one currency to be applied to purchases in another currency.|[How to: Allow for Application of Vendor Ledger Entries in Different Currencies](../how-to-allow-for-application-of-vendor-ledger-entries-in-different-currencies.md)|  
|Allow receipts in one currency to be applied to sales in another currency.|[How to: Allow for Application of Customer Ledger Entries in Different Currencies](../how-to-allow-for-application-of-customer-ledger-entries-in-different-currencies.md)|  
|Specify which currencies are EMU currencies.|[How to: Define EMU Currencies](../how-to-define-emu-currencies.md)|  
|Set up the general ledger accounts where rounding differences will be posted when you apply different currencies to each other.|[How to: Set Up General Ledger Accounts for Currency Application Rounding Differences](../how-to-set-up-general-ledger-accounts-for-currency-application-rounding-differences.md)|  
|Close entries applied in different currencies and post the rounding differences.|[How to: Allow for Rounding Differences When You Apply Entries in Different Currencies](../how-to-allow-for-rounding-differences-when-you-apply-entries-in-different-currencies.md)|  
  
## See Also  
 [Set Up Invoice Rounding](../set-up-invoice-rounding.md)   
 Adjust Add. Reporting Currency   
 [How to: Adjust Currency Exchange Rates](../how-to-adjust-currency-exchange-rates.md)