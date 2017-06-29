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
# Multiple Interest Rates Overview
For each finance charge term code, you can specify multiple interest rates so that you can calculate finance charges with multiple interest rates for a specific period. This is helpful if you charge different interest on payments that are late. The interest calculation is the same for each financial charge, with variation only in the rate of interest for a specific period.  
  
## Creating Finance Charges  
 When you create a finance charge memo, the memo lines show the finance charges with different interest rates for each time period. For finance charge terms, you can define descriptions for each term, and you can define a description that is used when multiple interest rates are used.  
  
 To use multiple interest rates, you must first define a finance charge term, and you must then add multiple interest rate lines to the terms. For more information, see [How to: Set Up Multiple Interest Rates](../FullExperience/how-to-set-up-multiple-interest-rates.md).  
  
 If no multiple interest rates exist, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> will use the interest rate and period that is defined in the **Finance Charge Terms** window for the whole period of calculation.  
  
## Delayed Payments  
 Multiple interest rates are used for different periods for delayed payments in trade transactions. For example, a government specifies the maximum interest to be levied for a consumer. This interest rate can be changed twice a year on 01 January and 01 July. The interest rate between businesses \(B2B\) is agreed by the parties and there is no limit to that customer group. The announced rate is usually four percent more than the normal bank interest.  
  
## See Also  
 [How to: Set Up Multiple Interest Rates](../FullExperience/how-to-set-up-multiple-interest-rates.md)   
 [Manage Finance Charges](../FullExperience/manage-finance-charges.md)