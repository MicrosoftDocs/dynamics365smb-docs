---
title: Activate SEPA Payments in the Dutch Version
description: To submit vendor payments electronically in Single Euro Payments Area (SEPA) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: submit vendor payments, SEPA, enable SEPA payments, electronic vendor payments, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Activate SEPA payments in the Dutch version

[!INCLUDE [activate-sepa-payments](../includes/BENL/activate-sepa-payments.md)]

## Configure the SEPA export format

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Export Protocols**, and then choose the related link.
1. Create or edit the export protocol for the required SEPA format.
1. Set **Export Object Type** to **Report**.
1. Set **Export ID** to **11000014** for SEPA credit transfers in pain.001.001.09 format, or **11000015** for SEPA direct debits in pain.008.001.08 format.
1. Configure **Check ID** for the payment scenario. Use **11000010** for SEPA validation or **11000011** for SEPA direct debit validation, which also checks the mandate.
1. Complete the remaining protocol fields, including the file naming settings.

Use separate export protocols for credit transfers and direct debits. Select the appropriate protocol on each transaction mode.

An export report doesn't determine the check codeunit automatically. Generic credit-transfer protocols can use a different **Check ID**. For example, the demo **GENERIC SEPA09** protocol pairs report **11000014** with check codeunit **11000007**. Don't replace a generic protocol's validation settings only because you change the export format.

## Enable transaction modes for SEPA  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Transaction Modes**, and then choose the related link.  
1. Select the transaction mode that you want to enable for SEPA, and then choose the **Edit** action.  
1. On the **Transaction Mode Card** page, on the **Paym. Proposal** FastTab, in the **Export Protocol** field, select the SEPA export protocol that you created, such as **SEPA ISO20022**.  
1. Verify **Our Bank**, select **Include in Payment Proposal**, and specify **Run No. Series**. The number series must allow default numbers.
1. Choose the **OK** button.  

## Verify vendor payment transaction modes for SEPA  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendors**, and then choose the related link.  
1. Select the vendor that you want to verify the transaction mode for, and then choose the **View** action.  
1. On the **Payments** FastTab, in the **Transaction Mode Code** field, verify that the vendor payment transaction mode is one that is enabled for SEPA.  
1. Choose the **OK** button.  

## Related information

- [Single EURO Payments Area (SEPA)](single-euro-payments-area-sepa-.md)  
- [Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format](how-to-submit-vendor-payments-electronically-in-sepa-iso-20022-payment-format.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
