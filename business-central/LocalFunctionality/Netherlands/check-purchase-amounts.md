---
    title: Check Purchase Amounts
    description: Before posting a purchase invoice or credit memo, application checks if the amount including VAT and the VAT amount stated on the purchase document is equal to the total amount of the inserted purchase lines.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Check Purchase Amounts
Before posting a purchase invoice or credit memo, application checks if the amount including VAT and the VAT amount stated on the purchase document is equal to the total amount of the inserted purchase lines. To do this, the **Doc. Amount Incl. VAT** and **Doc. Amount VAT** fields must be filled in in the **Purchase Invoice** or **Purchase Credit Memo** page.  

 In case there is only one purchase line or in case all lines are subject to the same VAT %, the correct **Doc. Amount VAT Field** will be calculated automatically when you have inserted the purchase lines and the **Doc. Amount Incl. VAT Field**. In case several lines exist with different VAT percentages, the **Doc. Amount VAT Field** must be changed manually.  

 Default application will check the purchase document total amounts, but you can switch it off by deselecting the **Check Doc. Total Amounts** check box on the **Purchases & Payables Setup** page.  

 To determine the reason of the difference between the document total amounts and the total amounts of the inserted purchase lines, you have the possibility to let application calculate the total amount, total base amount, total VAT amount and total amount including VAT of the inserted purchase lines and show them at the bottom of the purchase invoice or purchase credit memo page.  

 Default application will not show these total amounts, but you can switch it on by selecting the **Show Totals on Purch. Inv.-CM.** check box on the **Purchases & Payables Setup** page.  

> [!NOTE]  
>  If you activate this field, totals on all purchase invoices and credit memos must be recalculated. This can be a time-consuming process depending on the number of documents that must be recalculated. You can not activate this field in case purchase invoices and/or credit memos exist without any purchase lines or in case you have purchase invoices and/or purchase credit memos with no quantity specified on the lines.  

## See Also  
 [Set Up Validation of Purchase Amounts](how-to-set-up-validation-of-purchase-amounts.md)
