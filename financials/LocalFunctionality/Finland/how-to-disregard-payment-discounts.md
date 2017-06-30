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
# How to: Disregard Payment Discounts
Use the disregard payment discount at full payment feature to accept payments when the following conditions are true:  
  
-   Payment discount date \< payment date \<\= payment tolerance date  
  
-   Full amount \>\= payment amount \>\= full amount - payment discount  
  
### To disregard a payment discount  
  
1.  In the **Search** box, enter **Payment Terms**, and then choose the related link.  
  
2.  Select the line with the payment term for which you want to activate or deactivate payment discounts.  
  
3.  Select the **Disreg. Pmt. Disc. at Full Pmt** check box to initiate activation for this feature. To deactivate, clear the check box.  
  
> [!NOTE]  
>  When you apply one payment to multiple invoices, the feature to ignore payment discount at full payment is not supported.  
  
## See Also  
 [Electronic Banking in Finland](../electronic-banking-in-finland.md)   
 [How to: Generate Payment Files](../how-to-generate-payment-files.md)   
 [How to: Set Up Payment Terms](../how-to-set-up-payment-terms.md)   
 [Payment Tolerance and Payment Discount Tolerance](../payment-tolerance-and-payment-discount-tolerance.md)   
 [How to: Set Up Bank Reference Files](../how-to-set-up-bank-reference-files.md)