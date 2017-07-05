---
    title: Set Up Invoice Rounding | Microsoft Docs
    description: It may be necessary to round invoice amounts when you create invoices. Local regulations or local custom may require the invoice to be rounded in a specific way, for example, to an amount divisible by 0.05.
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
# Set Up Invoice Rounding
It may be necessary to round invoice amounts when you create invoices. Local regulations or local custom may require the invoice to be rounded in a specific way, for example, to an amount divisible by 0.05.  
  
 The automatic invoice rounding function can handle these situations. When an invoice is rounded, an extra line is inserted with the rounding amount and this line is posted along with the other invoice lines.  
  
 To use automatic invoice rounding, you must:  
  
-   Specify the general ledger accounts to which rounding differences will be posted.  
  
-   Set up rules for rounding invoices in local currency and in foreign currency.  
  
-   Activate the function.  
  
> [!NOTE]  
>  In addition to the invoice rounding features, amounts on invoices can be rounded by the unit-amount rounding feature and the amount rounding feature. For more information, see [Set Up Currencies](../set-up-currencies.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Set up the general ledger accounts where invoice rounding differences will be posted.|[How to: Set Up General Ledger Accounts for Invoice Rounding Differences](../how-to-set-up-general-ledger-accounts-for-invoice-rounding-differences.md)|  
|Set up rounding rules to use the automatic invoice rounding function for invoices in local currency.|[How to: Set Up Rounding Rules for the LCY](../how-to-set-up-rounding-rules-for-the-lcy.md)|  
|Set up rounding rules to use the automatic invoice rounding function for invoices in foreign currency.|[How to: Set Up Rounding Rules for Foreign Currency](../how-to-set-up-rounding-rules-for-foreign-currency.md)|  
|Activate the invoice rounding function so that sales and purchase invoices are rounded automatically.|[How to: Enable the Invoice Rounding Function](../how-to-enable-the-invoice-rounding-function.md)|  
  
## See Also  
 [Set Up Currencies](../set-up-currencies.md)   
 [How to: Allow for Rounding Differences When You Apply Entries in Different Currencies](../how-to-allow-for-rounding-differences-when-you-apply-entries-in-different-currencies.md)