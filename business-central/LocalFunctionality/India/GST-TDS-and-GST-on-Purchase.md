---
title: Calculation of Income Tax TDS and GST on Purchase Transactions
description: Calculate income tax TDS and GST on purchase transactions, and review illustrative calculation and accounting entries in Business Central for India.
author: v-debapd  
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, income tax TDS, TDS, purchase transactions
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Calculation of Income Tax TDS and GST on purchase transactions

There are certain services on which GST applies along with the provisions of TDS under income tax. TDS shouldn't be calculated on GST amount, in some cases where payment terms are set as 100% advance, full order value has to be paid as advance payment. In such cases, amount paid to vendor is inclusive of GST and if TDS has to be deducted while paying amount to vendor, then TDS is deducted only on the base amount and not on the GST amount.

The following examples use illustrative GST and TDS rates. Actual calculation depends on the GST setup, the vendor's allowed TDS sections, and the configured tax rates.

## Create a purchase invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Invoices**, and then choose the related link.
1. Select **Vendor** on **Invoice Header**.
1. Select **G/L Account** for the service on the invoice line. Check **GST Group Code** and **HSN/SAC Code**. Set **GST Credit** to **Availment** or **Non-Availment**, as appropriate.
1. Select **TDS Section Code** on the invoice line. The lookup shows sections allowed for the vendor.

Changing **TDS Section Code** recalculates tax for the document. Check the tax calculation after selecting the section and before posting the invoice.

For example, there's a purchase invoice for INR 10,000 and 18% GST (that is, 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged and Income Tax TDS @10% also to be charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Transaction Value**|10000|
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|
    |**TDS**|1000|

- GL Entries for Income Tax TDS and GST in Intra-State purchase transactions are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-10800|

- GL Entries for Income Tax TDS and GST in Intra-State or Intra-Union Territory purchase transactions (reverse charge) are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable Account (Interim)**|900|  
    |**CGST Receivable Account (Interim)**|900|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-9000|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**CGST Payable (Interim) Account**|-900|

- GL Entries for Income Tax TDS and GST in Inter-State purchase transactions are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|
    |**IGST Receivable Account**|1800|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-10800|

- GL Entries for Income Tax TDS and GST in Inter-State purchase transactions (reverse charge) are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|
    |**IGST Receivable Account (Interim)**|1800|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-9000|
    |**IGST Payable (Interim) Account**|-1800|

## Related information

[Purchase Return to Composite Vendor](GST-Purchase-Return-to-Composite-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
