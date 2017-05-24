---
title: "Swiss Value Added Tax"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, amounts and exchange rates"
  - "VAT, Swiss"
ms.assetid: 0edace66-a335-4c97-870a-e51bddd27fa8
caps.latest.revision: 4
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# Swiss Value Added Tax
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes the following enhancements to Swiss VAT reporting:  
  
-   Automatic adjustment of VAT amounts for invoices, according to payment discounts.  
  
-   Additional VAT exchange rates for invoices in foreign currencies.  
  
-   VAT percentages and amounts included in journals.  
  
 For more information about Swiss VAT reporting and coding requirements, see [Swiss VAT Information](http://www.estv.admin.ch/mwst/dokumentation/00130/00947/00948/index.html?lang=fr), in particular, document 605.525.01. The information is available in French, German, and Italian.  
  
## VAT Amounts and VAT Exchange Rates  
 According to local VAT laws, the VAT base amount for an invoice can be reduced by the payment discount if a discount is granted. To allow automatic VAT adjustment for a payment discount on an invoice, the **\($ T\_98\_49 Adjust for Payment Discount $\)** field is activated by default in the **\($ N\_118 General Ledger Setup $\)** window. You can also activate this function in the VAT posting setup. For more information, see the [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6) table and the [\($ T\_325 VAT Posting Setup $\)](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f) table.  
  
### Currency Exchange Rates for VAT Reporting  
 For invoices in foreign currency, you must use the official exchange rate provided by the government for the VAT calculation itself. You can also set up additional exchange rates for VAT, which you can use for aspects of the invoice other than the VAT calculation. You can provide the correct government VAT exchange rate for each relevant foreign currency in the exchange rate setup for invoices. For more information, see the [\($ T\_330 Currency Exchange Rate $\)](assetId:///b0b89d1c-bc67-4cc9-ba62-20ddd368452c) table.  
  
 You can also adjust all VAT amounts in VAT entries that result from foreign currency transactions. When you activate the adjust VAT exchange rate function, VAT exchange rates are adjusted automatically. The positive differences that result from exchange rates are posted to exchange rate gain accounts. The negative differences that result from exchange rates are posted to exchange rate loss accounts. For more information, see the [\($ B\_595 Adjust Exchange Rates $\)](../Topic/\($%20B_595%20Adjust%20Exchange%20Rates%20$\).md) batch job.  
  
 Additional information, such as VAT rate and original currency amount, is transferred to the VAT entries. For more information, see the [\($ T\_254 VAT Entry $\)](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32) table.  
  
### VAT Information in Journals  
 When you enter a new line in a journal, the VAT percentages and VAT amounts for the account and balance account for the selected journal line are populated in the journal status area. For more information, see the [\($ N\_39 General Journal $\)](assetId:///a60a346f-f336-47bb-b046-55a1595e1555) window, [\($ N\_253 Sales Journal $\)](../Topic/\($%20N_253%20Sales%20Journal%20$\).md) window, and the [\($ N\_254 Purchase Journal $\)](../Topic/\($%20N_254%20Purchase%20Journal%20$\).md).  
  
## See Also  
 [VAT Rates for Switzerland](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/vat-rates-for-switzerland.md)   
 [How to: Create and Print a Swiss VAT Statement](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-create-and-print-a-swiss-vat-statement.md)   
 [\($ R\_26100 Swiss VAT Statement $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-r_26100-swiss-vat-statement-$-.md)   
 [Switzerland Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/switzerland-local-functionality.md)   
 [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)   
 [\($ T\_325 VAT Posting Setup $\)](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f)   
 [\($ B\_595 Adjust Exchange Rates $\)](../Topic/\($%20B_595%20Adjust%20Exchange%20Rates%20$\).md)   
 [\($ T\_330 Currency Exchange Rate $\)](assetId:///b0b89d1c-bc67-4cc9-ba62-20ddd368452c)   
 [\($ T\_254 VAT Entry $\)](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32)   
 [\($ N\_39 General Journal $\)](assetId:///a60a346f-f336-47bb-b046-55a1595e1555)   
 [\($ T\_81 Gen. Journal Line $\)](assetId:///5308c791-0964-41d9-bc54-fd87e815d1be)   
 [\($ N\_253 Sales Journal $\)](../Topic/\($%20N_253%20Sales%20Journal%20$\).md)   
 [\($ N\_254 Purchase Journal $\)](../Topic/\($%20N_254%20Purchase%20Journal%20$\).md)