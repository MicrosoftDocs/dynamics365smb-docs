---
title: Export remittance payments [NO]
description: This article explains how you can use the export remittance payments process to export the payments file to your computer in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 12/08/2023
ms.author: bholtorf
---
# Export remittance payments in the Norwegian version

You can use the export remittance payments process to export the payments file to your computer. You can then transfer the remittance payments to the bank.  

> [!IMPORTANT]  
>  Before you can export a remittance payment, you must select a payment format in the **Payment Export Format** field on the **Bank Account Card** page.  

You export payments to a bank file by choosing the **Export Payments** button on the **Payment Journal** page. The process might be different, depending on the export format that you select:  

- Payments using the SEPA payment standard are directly exported to a file when you choose the **Export Payments** button. For more information, see [Making Payments](../../payables-make-payments.md).  

- Payments using local payment standards, such as **Telepay**, are exported with either the **Remittance - export (bank)** or the **Remittance - export (BBS)** report, which automatically opens when you choose the **Export Payments** button.  

The procedure for exporting payments using the **Remittance – Export** batch job is described in this article.  

## To export remittance payments using the remittance - Export batch jobs  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
2.  Prepare to export the payments from the journal. For more information, see [Export Payments to a Bank File](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).  
3.  Choose the **Export Payments** action.  
4.  In the report page that opens, choose the **Options** FastTab, and fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance agreement code**|Specify the code for the agreement.|  
    |**Operator**|Specify the operator number.|  
    |**Password**|Specify the password for the payments.|  
    |**Division**|Specify the division that is paying remittance.|  
    |**Current note**|Specify a note for the payment.|  
    |**Filename**|Specify the name and directory of the payment file.|  

5.  Choose the **OK** button.  

The payment information is exported to the file that is set up in the remittance agreement.  

The payment journal is deleted and the transactions are transferred to the waiting journal.  

## See also  
 [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)   
 [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)   
 [Create Remittance Accounts](how-to-create-remittance-accounts.md)   
 [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](recipient-reference-codes.md)   
 [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)   
 [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)   
 [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)   
 [Test Remittance Payments](how-to-test-remittance-payments.md)   
 [Types of Payment Returns Files](types-of-payment-returns-files.md)   
 [Import Payment Return Data](how-to-import-payment-return-data.md)   
 [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](remittance-errors.md)   
 [View Remittance Error Codes](how-to-view-remittance-error-codes.md)   
 [Cancel Payments](how-to-cancel-payments.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]