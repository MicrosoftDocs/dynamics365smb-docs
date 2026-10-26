---
title: Import Payment Return Data in the Norwegian Version [NO]
description: Import Norwegian remittance receipt and settlement return files into an empty payment journal in Business Central, then review settlement warnings.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import return data, settlement returns, import receipt and settlement returns, Norwegian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import payment return data in the Norwegian version

To import receipt and settlement returns, use the **Rem. payment order – import** page. If any errors are indicated when importing settlement returns, you can view this information on the **Settlement Info** page.  

## Import return data  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Journals**, and then choose the related link.
1. Open an empty journal batch for the returned payments, and then choose **Import Return Data**. The journal batch must be empty before import.
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment order note**|Enter a note that is transferred to the payment order.|  
    |**Control batch**|Select to check whether return files can be imported without saving the imported data.|
    |**Return files**|Specifies how many return files are found and imported.|  

1. Choose the **Return Files** button to display the return files.  
1. On the **Return Files** page, select the **Import** option next to each file to be imported. If the option is cleared, the file won't be imported.  
1. Choose the **OK** button.  

## View settlement information  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Journals**, and then choose the related link.
1. Select the returned payment line, and then choose **Settlement Info**.
1. On the **General** FastTab, view the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance Handling Ref.**|Shows the reference that the bank enters for foreign payments.|  
    |**Remittance Warning**|If selected, the journal line contains a warning.|  
    |**Remittance Warning Text**|Shows the description of the warning, if applicable.|  

1. Choose the **OK** button.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
- [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
- [Recipient Reference Codes](recipient-reference-codes.md)
- [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)
- [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)
- [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)
- [Test Remittance Payments](how-to-test-remittance-payments.md)
- [Export Remittance Payments](how-to-export-remittance-payments.md)
- [Types of Payment Returns Files](types-of-payment-returns-files.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
