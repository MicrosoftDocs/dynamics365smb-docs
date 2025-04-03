---
title: Submit Vendor Payments Electronically in SEPA ISO 20022 Format (NL)
description: In the Dutch version of Business Central, you can electronically create and submit vendor payments in the Single Euro Payments Area (SEPA) ISO 20022 format.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: create vendor payments, submit vendor payments, SEPA ISO 20022, Dutch version, Netherlands
ms.date: 03/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Submit vendor payments electronically in SEPA ISO 20022 payment format

In the Dutch version of [!INCLUDE[prod_short](../../includes/prod_short.md)], you can create and submit Single Euro Payments Area (SEPA) ISO 20022 vendor payments electronically.  

Before you can create and submit SEPA vendor payments, you must enable SEPA payments. Learn more in [Activate SEPA Payments](how-to-activate-sepa-payments.md).  

## Process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Telebank-Bank Overview**, and then choose the related link.  
1. Select the relevant bank account, and then choose the **Proposal** action.  
1. Select the relevant vendor bank account, and then choose the **Get Entries** action.  
1. In the **Get Proposal Entries** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Currency Date**|Specify the currency date.|  
    |**Pmt. Discount Date**|Specify the payment discount date.|  

1. On the **Transaction Mode** FastTab, select the appropriate filters.  
1. On the **Cust. Ledger Entry** FastTab, select the appropriate filters.  
1. On the **Vendor Ledger Entry** FastTab, select the **Vendor No.** filter, and then select a vendor number.  

   > [!NOTE]
   > Select other appropriate filters if required.  

1. Choose the **OK** button.  

The proposal lines populate on the **Telebank Proposal** page.  

## Related information

- [Activate SEPA Payments](how-to-activate-sepa-payments.md)
- [Single EURO Payments Area (SEPA)](single-euro-payments-area-sepa-.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
