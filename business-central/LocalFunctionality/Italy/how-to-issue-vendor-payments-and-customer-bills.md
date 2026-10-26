---
title: Issue Vendor Payments and Customer Bills
description: Learn how to prepare vendor payment details, create an issued bill list, and export a bank payment file in the Italian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: vendor and customer bill pay feature, issue vendor payments, issue customer bills, SEPA credit transfer, SEPA direct debit, vendor bill payment, customer bill payment, Italian version
ms.search.form: 12102, 12175, 12176, 12178, 12180, 12181, 12182, 12184, 12185, 12186, 12190
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Issue vendor payments and customer bills

The vendor and customer bill pay feature supports SEPA-based formats in addition to Italian file formats. You can pay vendors according to the SEPA Credit Transfer standard and collect payment from customers according to the SEPA Direct Debit standard. The following procedure describes the process for sending a SEPA-based payment to a vendor. The steps are similar for collecting payment from a customer.  

Before starting the following procedure, make sure that information for your company's bank is provided on the **Bank Account Card** page. On the card, include information for the following fields:  

- IBAN  
- SWIFT Code (optional)  
- Payment Export Format  
- SEPA CT Msg. ID No. Series  

You also need a posted purchase invoice to pay. The payment method must have a **Bill Code**.

## Prepare the vendor's payment details

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendors**, and then choose the related link.  
1. Open the vendor card. In **Payment Method Code**, select the bank-transfer payment method that you've configured. Payment method codes depend on your company's setup.
1. Choose the **Bank Accounts** action.  
1. In the **Vendor Bank Account List**, select the vendor's bank account, and then choose the **Edit** action.
1. On the **Transfer** FastTab, specify information for the **IBAN** field.  
1. Choose the **OK** button.  
## Create the vendor bill list

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendor Bill Card**, and then choose the related link.
1. Choose the **New** action.  
1. On the **General** FastTab, select your company's paying bank account in **Bank Account No.** and enter **Payment Method Code**. Review the list and posting dates.
1. Choose the **Suggest Payment** action.
1. Set filters, as appropriate, and then choose the **OK** button to run the batch job.  
1. Choose the **Create List** action.
1. Confirm that you want to create the list.

## Export the issued list

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendor Bill List Issued**, and choose the related link.
1. Select the bill payment that you issued from the list, and then choose the **Edit** action. The **Vendor Bill List Sent Card** page opens.  
1. Choose **Export Bill List to File**. The export uses the **Payment Export Format** on your company's bank account.
1. Review and fix any errors shown in the **File Export Errors** FactBox, and export again if needed.
1. Review the downloaded file, and submit it through your bank's payment service.

Creating or exporting the bill list doesn't transfer funds to the vendor. Follow your bank's submission and authorization process.

## Related information

- [Set up automatic payments and automatic bills](how-to-set-up-automatic-payments-and-automatic-bills.md)
- [Make payments with SEPA credit transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)
- [Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
