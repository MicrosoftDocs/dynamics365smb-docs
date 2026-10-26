---
title: Export Remittance Payments in the Norwegian Version [NO]
description: Export Norwegian remittance payments to a bank file in Business Central, review the export report options, and transfer payments to the waiting journal.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export remittance payment, remittance payment files, remittance payments process, transfer remittance payments, payment journal, waiting journal, Norwegian version
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Export remittance payments in the Norwegian version

You can use the export remittance payments process to export the payments file to your computer. You can then transfer the remittance payments to the bank.  

> [!IMPORTANT]  
> Before you can export a remittance payment, you must select a payment format in the **Payment Export Format** field on the **Bank Account Card** page.  

You export payments to a bank file by choosing the **Export Payments** button on the **Payment Journal** page. The process might be different, depending on the export format that you select:  

- Payments using the SEPA payment standard are directly exported to a file when you choose the **Export Payments** button. Learn more in [Making Payments](../../payables-make-payments.md).  

- Payments using local payment standards, such as **Telepay**, are exported with either the **Remittance - export (bank)** or the **Remittance - export (BBS)** report, which automatically opens when you choose the **Export Payments** button.  

The procedure for exporting payments using the **Remittance – Export** batch job is described in this article.  

## Export remittance payments with the remittance export batch jobs

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Journals**, and then choose the related link.  
1. Prepare to export the payments from the journal. Learn more in [Export Payments to a Bank File](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).  
1. Choose the **Export Payments** action.  
1. In the **Remittance - export (bank)** report page, choose the **Options** FastTab, and fill in the fields as described in the following table. If the agreement uses **BBS**, the **Remittance - export (BBS)** report opens instead. It has **Remittance agreement code**, **Payment order note**, and **Filename** fields.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance agreement code**|Specify the code for the agreement.|  
    |**Operator**|Specify the operator number.|  
    |**Password**|Specify the password for the payments.|  
    |**Division**|Specify the division that is paying remittance.|  
    |**Current note**|Specify a note for the payment.|  
    |**Filename**|Specify the name and directory of the payment file.|  

1. Choose the **OK** button.  

The payment information is exported to the file that is set up in the remittance agreement.  

The exported journal lines are deleted from the payment journal and transferred to the waiting journal with a status of **Sent**. The journal batch isn't deleted. Submit the exported file through your bank's software to send the payments to the bank.

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
- [Types of Payment Returns Files](types-of-payment-returns-files.md)
- [Import Payment Return Data](how-to-import-payment-return-data.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
