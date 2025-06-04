---
title: Test Remittance Payments [NO]
description: Learn how to test payment journal lines for errors before posting, after setting up remittance payments and generating suggestions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: test remittance payments, remittance test report, payment journal lines, remittance payments, Norwegian version
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Test remittance payments in the Norwegian version

After setting up remittance payments and generated suggestions, you can test the payment journal lines for errors before posting them.  

To test the payment journal lines, you can use the **Remittance Test** report. This report prints an overview of all journal lines together with any errors, such as missing fields or incorrect bank accounts.  

If a warning is printed in the test report, you can't transfer the payments to the bank before the problem is corrected. You should print the test report to make sure that all payments are made as expected.  

## Print a remittance test report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
1. Choose the **Test Report** action.  
1. On the **Options** FastTab, select the **Show Dimensions** field to print dimensions on the test report.  
1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
- [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
- [Recipient Reference Codes](recipient-reference-codes.md)
- [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)
- [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)
- [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)
- [Export Remittance Payments](how-to-export-remittance-payments.md)
- [Types of Payment Returns Files](types-of-payment-returns-files.md)
- [Import Payment Return Data](how-to-import-payment-return-data.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
