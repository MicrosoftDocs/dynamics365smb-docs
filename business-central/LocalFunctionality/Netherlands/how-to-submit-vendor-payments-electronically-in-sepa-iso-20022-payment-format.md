---
title: Submit Dutch Vendor Payments in SEPA ISO 20022 Format
description: In the Dutch version of Business Central, you can electronically create and submit vendor payments in the Single Euro Payments Area (SEPA) ISO 20022 format.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: create vendor payments, submit vendor payments, SEPA ISO 20022, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Submit vendor payments electronically in SEPA ISO 20022 payment format

In the Dutch version of [!INCLUDE[prod_short](../../includes/prod_short.md)], you can create and submit Single Euro Payments Area (SEPA) ISO 20022 vendor payments electronically.  

Before you can create and submit SEPA vendor payments, you must enable SEPA payments. Learn more in [Activate SEPA Payments](how-to-activate-sepa-payments.md).  

## Create and export vendor payments

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Telebank - Bank Overview**, and then choose the related link.
1. Select the relevant bank account, and then choose the **Proposal** action.  
1. Choose the **Get Entries** action.
1. In the **Get Proposal Entries** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Currency Date**|Specify the currency date.|  
    |**Pmt. Discount Date**|Specify the payment discount date.|  

1. On the **Transaction Mode** FastTab, set **Account Type** to **Vendor** and select the relevant SEPA transaction mode. This filter excludes customer collections and employee payments.
1. On the **Vendor Ledger Entry** FastTab, select the **Vendor No.** filter, and then select a vendor number.  

1. Choose the **OK** button.  
1. On the **Telebank Proposal** page, review the proposal lines, including the vendor bank accounts and amounts. Choose **Check** and resolve any errors.
1. Choose **Process** to create the payment history.
1. Close the proposal page. On **Telebank - Bank Overview**, keep the same bank account selected and choose **Payment History**.
1. Select the payment history and choose **Export**. Complete any export options to download the payment file.

Submit the exported file through your bank's banking software or portal. Exporting the payment history doesn't send the payment instructions to the bank.

## Related information

- [Activate SEPA Payments](how-to-activate-sepa-payments.md)
- [Single EURO Payments Area (SEPA)](single-euro-payments-area-sepa-.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
