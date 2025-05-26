---
title: Set Up Vendors for Remittance [NO]
description: Learn how to set up vendors for remittance to automate payments and minimize manual entry errors.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: vendors for remittance,, remittance vendors, remittance setup, Norwegian version, remittance payments
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up vendors for remittance in the Norwegian version

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Norwegian enhancements for automatically making payments to vendors. This reduces errors that occur from manual data entry. To pay vendors using the remittance system, you must set up vendor information.  

## Set up a vendor for remittance  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. Choose the **Edit** action.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|Specify the vendor’s name. This field is used by remittance against Bankernes Betalingssentral (BBS).|  
    |**Address**|Specify the vendor’s address. This field is used by remittance against BBS.|  
    |**Address 2**|Specify an additional line for the vendor’s address, if necessary. This field is used by remittance against BBS.|  
    |**Post Code**|Specify a valid postal code of four digits for domestic remittance.|  
    |**Country/Region Code**|Specify a valid country/region code for a foreign address.|  

1. On the **Payments** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance**|Select if the vendor is to be remitted.|  
    |**Remittance Account Code**|Specify the account code to be used for the vendor.|  
    |**Recipient Bank Account No.**|Specify the account number used to remit the vendor.|  

1. Choose the **Remittance Info** action.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance Account Code**|Specify the code of the remittance account which the vendor is using.|  
    |**Remittance Agreement Code**|Specify the code of the agreement to which the account is linked.|  
    |**Recipient Bank Account No.**|Specify the vendor's account number used for remittance.|  

1. On the **Domestic** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Own vendor recipient ref.**|Select to use the recipient reference from the vendor.|  
    |**Recipient ref. 1 -- inv.**|Enter the text that prints on the payment invoice.|  
    |**Recipient ref. 1 - cred.**|Enter the text that prints on the payment invoice when deducting a credit memo.|  

    If remittance to BBS is used, the text from **Recipient ref. - inv.** and **Recipient ref. -cred.** is displayed on the payment specification in lines one through three, columns one and two. You can insert a maximum of 80 characters on the payment specification.  

    The text in the recipient reference fields can be formatted automatically with special codes. Learn more in [Recipient Reference Codes](recipient-reference-codes.md).  

1. On the **Payment abroad** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recipient Ref. Abroad**|Enter the text that prints on the payment invoice.|  
    |**Warning Notice**|Select one of the following options to specify how a warning notice is sent from the recipient's bank to the recipient.<br>- **None**: No confirmation is sent.<br>- **Phone**: Confirmation is given by phone.<br>- **Fax**: Confirmation is sent by fax.<br>-   **Other** - A text message in the **Warning Text** field is used.|  
    |**Warning Text**|Enter the warning text that is used if the **Warning Notice** field is set to **Other**.|  
    |**Recipient Confirmation**|Select to specify how confirmation of payment is sent to the recipient.|  
    |**Telex Country/Region Code**|Specify the country/region code if the confirmation is sent using telex.|  
    |**Telex/Fax No.**|Specify the telex or fax number if the confirmation is sent using telex or fax.|  
    |**Recipient Contact**|Specify the contact person’s name if a telex or fax confirmation is sent to the recipient.|  
    |**Charges Domestic**|Specify who is charged the domestic charges in connection with the payment.<br>- **Debitremitter**: The remitter is charged.<br>- **Debitrecipient**: The recipient is charged.<br>- **Default**: The bank's way of charging is used. Typically this is the remitter who is charged.|  
    |**Charges Abroad**|Specify who is charged for foreign payments.<br>- **Debitremitter**: The remitter is charged.<br>- **Debitrecipient**: The recipient is charged.<br>- **Default**: The bank's way of charging is used. Typically this is the remitter who is charged.|  
    |**Payment Type Code Abroad**|Enter a two-digit code for the payment type.|  
    |**Specification (Norges Bank)**|Specify information for your local government bank. Contact your bank for further information.|  

1. On the **Bank abroad** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**SWIFT**|Enter the Society for Worldwide Interbank Financial Telecommunication (SWIFT) address by which the recipient’s bank is identified.|  
    |**Bank Name**|Specify the bank's name.|  
    |**Bank Address 1**|Specify the address of the recipient's bank.|  
    |**Rcpt. Bank Country/Region Code**|Specify the country/region code for the recipient. This field is required and must comply with ISO standards.|  
    |**SWIFT Remb. Bank**|Specify the SWIFT address for reimbursement that is the recipient’s corresponding bank.|  

1. Choose the **OK** button.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
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
