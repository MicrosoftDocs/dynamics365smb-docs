---
    title: How to Test Electronic Payments
    description: After you have set up electronic banking and generated payment suggestions, you can test the payment journal lines for errors before posting them.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Test Electronic Payments
> [!Note]
> [!INCLUDE[onprem_only](../../includes/onprem_only_md.md)]

After you have set up electronic banking and generated payment suggestions, you can test the payment journal lines for errors before posting them.  

Some of the information that is validated includes:  

- Bank accounts numbers are valid.  
- Positive payment lines are present.  
- If domestic and international payments are made from only one bank account.  
- If only one bank account can be used for Isabel.  
- If payment lines are in Euro for SEPA.  
- If a number series has been defined for SEPA.  

You can view any errors in the **Export Check Error Logs** window.  

> [!IMPORTANT]  
>  You have to correct all errors before you can post the lines.  

## To test payment journal lines  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select the required journal batch.  
3.  In the **Export Protocol** field, select the export protocol.  
4.  Enter the payment journal line information, and then choose the **Check Payment Lines** action to validate the payment journal lines. The validation that is performed on the journal lines depends on the type of check that is specified in the **Export Protocols** window.  

## See Also  
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [Generate Payment Suggestions](how-to-generate-payment-suggestions.md)   
 [Print Payment Files](how-to-print-payment-files.md)
