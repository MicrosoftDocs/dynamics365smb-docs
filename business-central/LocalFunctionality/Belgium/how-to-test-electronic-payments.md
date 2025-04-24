---
title: Test Electronic Payments [BE]
description: After electronic banking is set up and payment suggestions are generated, the payment journal lines can be tested for errors before posting them.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic payments, test electronic payments, payment journal lines, Belgian version
ms.search.form: 2000001
ms.date: 04/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Test electronic payments in the Belgian version

After you set up electronic banking and generated payment suggestions, you can test the payment journal lines for errors before posting them.  

Some of the information that is validated includes:  

- Whether bank account numbers are valid.  
- Whether positive payment lines are present.  
- Whether domestic and international payments are made from only one bank account.  
- Whether only one bank account can be used for Interbanks Standards Association Belgium (Isabel).  
- Whether payment lines are in euro for Single Euro Payments Area (SEPA).  
- Whether a number series is defined for SEPA.  

You can view any errors on the **Export Check Error Logs** page.  

> [!IMPORTANT]  
> You have to correct all errors before you can post the lines.  

## Test payment journal lines  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the link to open the **EB Payment Journals** page.  
1. In the **Batch Name** field, select the required journal batch.  
1. In the **Export Protocol** field, select the export protocol.  
1. Enter the payment journal line information, and then choose the **Check Payment Lines** action to validate the payment journal lines. The validation that is performed on the journal lines depends on the type of check that is specified on the **Export Protocols** page.  

## Related information

- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)  
- [Belgian Electronic Payments](belgian-electronic-payments.md)  
- [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)  
- [Suggest Vendor Payments](../../payables-how-suggest-vendor-payments.md)  
- [Print Payment Files](how-to-print-payment-files.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
