---
title: Set Up Remittance Agreements [NO]
description: Learn how to set up remittance agreements with your bank for electronic payments in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: remittance agreement, remittance agreement setup, Norwegian version
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up remittance agreements in the Norwegian version

You must sign an agreement of remittance with the bank when you set up electronic payments. You can create more than one remittance agreement if you have an agreement with two or more banks. For each agreement, you must specify one or more accounts from which the payment should be made. For each account, you must create a remittance account. Learn more in [Create Remittance Accounts](how-to-create-remittance-accounts.md).  

## Set up a remittance agreement  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Remittance Agreement Overview**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the agreement code from the bank.|  
    |**Description**|Specify a name for the agreement, such as the name of the bank.|  
    |**Payment System**|Select the payment system that is used. Payment systems include **DnB Telebank**, **K-LINK**, **SparNett**, **Fokus Bank**, **Postbanken**, **Other bank**, and **BBS**.|  

1. On the **Bank** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Operator No.**|Specify the operator information given by the bank.|  
    |**Company/Agreement No.**|Specify the company information given by the bank.|  
    |**Division**|Specify the division information given by the bank.|  
    |**Latest Sequence No.**|Specify the latest sequence number.|  
    |**Latest Daily Sequence No.**|Specify the latest daily sequence number.|  
    |**Latest Export**|Specify the date of the latest export.|  

1. On the **BBS** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**BBS Customer Unit ID**|Specify the identification of the agreement for Bankernes Betalingssentral (BBS). This code is provided by BBS.|  
    |**Latest BBS Payment Order No.**|Specify the entry number that was used when payment was sent to BBS.|  

1. On the **Send** FastTab, fill in the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment File Name**|Specify the path and the name of the file that contains the electronic payment order that was sent to the bank.|  

1. On the **Receive** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----------|---------------------------------------|  
    |**Save Return File**|Select to automatically name the return file after it's imported without errors.|  
    |**Receipt Return Required**|Select to verify that the first-time return report is imported.|  
    |**Return File Is Not In Use**|Select if you don't want to use return files for approval and settlement of payment. You can use this feature if you don't want to update payments with return information from the bank.|  
    |**On Hold Rejection Code**|Enter the code to update a rejected vendor ledger entry. The ledger entry is marked as **On Hold**, which means that after rejection, it isn't added to the remittance proposal again.<br> If the code is blank, the entry isn't marked as **On Hold**, which means that after rejection it can be added to a remittance proposal again.|  

1. On the **Finance** FastTab, fill in the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**New Document Per Field**|Specify how documents are numbered when payments are posted. Options include **Date**, **Vendor**, and **Specified for account**.|  

1. Choose the **Return File Setup List** action.  
1. On the **Return File Setup List** page, choose the **New** action.  
1. Enter the return file name in the **Return File Name** field.  

    > [!NOTE]  
    > At a minimum, you must set up one file name for each receipt return, rejected return, and settlement return. Contact your bank about the naming conventions that it uses.  

1. Choose the **OK** button.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
- [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
- [Recipient Reference Codes](recipient-reference-codes.md)
- [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)
- [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)
- [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)
- [Test Remittance Payments](how-to-test-remittance-payments.md)
- [Export Remittance Payments](how-to-export-remittance-payments.md)
- [Types of Payment Returns Files](types-of-payment-returns-files.md)
- [Import Payment Return Data](how-to-import-payment-return-data.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
