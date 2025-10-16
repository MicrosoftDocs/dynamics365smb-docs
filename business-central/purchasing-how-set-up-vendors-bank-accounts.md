---
title: Set Up Vendor Bank Account
description: Learn how to associate bank accounts to vendor cards in Business Central, including contact information, SWIFT, and IBAN codes.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 10/03/2025
ms.author: bholtorf
ms.reviewer: v-soumramani
---

# Set up vendor bank accounts

Just as you can use bank account information on [!INCLUDE [prod_short](includes/prod_short.md)] to keep track of your company's banking transactions, you can also set banking details for vendors. Vendor bank account data can simplify payments to suppliers when combined with the [AMC Banking 365 Fundamentals Extension](ui-extensions-amc-banking.md) or the [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md) feature, for example.

## Add or edit a vendor bank account

[!INCLUDE [purchase-vendor-bank-account](includes/purchase-vendor-bank-account.md)]

> [!TIP]
> You can set additional vendor bank accounts on the **Vendor Bank Account List** page.

## Set up a preferred vendor bank account

If a vendor has one or more bank accounts and you want to set a preferred option for the payment journal lines, follow these steps:

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the card for the vendor.
3. On the **Payments** FastTab, choose the default vendor bank account in the **Preferred Bank Account Code** field.

## Related information

[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Set Up Bank Accounts](bank-how-setup-bank-accounts.md)  
[Use the AMC Banking 365 Fundamentals Extension](ui-extensions-amc-banking.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
