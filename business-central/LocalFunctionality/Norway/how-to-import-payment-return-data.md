---
title: How to import payment return data [NO]
description: Learn how to use the Rem. payment order – import page to import receipt and settlement returns efficiently.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import return data, settlement returns, import receipt and settlement returns, Norwegian version
ms.date: 05/13/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Import payment return data in the Norwegian version

To import receipt and settlement returns, use the **Rem. payment order – import** page. If any errors are indicated when importing settlement returns, you can view this information on the **Settlement Info** page.  

## Import return data  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Rem. payment order – import**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment order note**|Enter a note that is transferred to the payment order.|  
    |**ControlBatch**|Select the checkbox to verify return files in advance to ensure if the import can be made. Return data isn't imported.|  
    |**Return files**|Specifies how many return files are found and imported.|  

1. Choose the **Return Files** button to display the return files.  
1. On the **Return Files** page, select the **Import** option next to each file to be imported. If the option is cleared, the file won't be imported.  
1. Choose the **OK** button.  

## View settlement information  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Settlement Info**, and then choose the related link.  
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
