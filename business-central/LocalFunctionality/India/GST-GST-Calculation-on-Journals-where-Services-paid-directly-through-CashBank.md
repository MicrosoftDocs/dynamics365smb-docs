---
title: GST on Journals where Services paid directly through Cash or Bank
description: Explains GST calculation on journals for services paid directly via cash or bank in Business Central India localization.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English. GST on journals
ms.date: 10/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: soumramani
---

# GST on journals for services paid directly through cash or bank

You can post invoices and credit memos from journals. The GST calculation logic applied to journals is same as the logic used for documents.

This article explains the GST calculation process.

## Create a general journal or a bank or cash payment voucher

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.
1. Select **Party Type**, **Party Code**, and **Location Code**.

   > [!NOTE]
   > You must set the GST **Party Type** to **Vendor**, and the GST vendor type in **Party Code** should be **Unregistered**.

1. Select **G/L Account** in account type and **G/L Account** or **Bank Account** in balancing account type, and then select the cash or bank accounts.
1. GST (CGST/SGST/UTGST/IGST) to be calculated on Direct Expenses (Services) being paid through cash or bank, any legal fees, telephone expenses, etc.

## Example

For example, there's an expense of INR 10,000 and 18% GST (that is, 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on expense amount.

### GST calculations in the Fact Box

In this example, GST calculations appear in the Fact Box as shown in the following table.

| Component | Amount |
|--|--|
| **GST Base Amount** | 10,000 |
| **CGST** | 900 |
| **SGST** | 900 |
| **IGST** | 1800 |

### GL entries for intra-state or intra-union territory purchase

For this example, the following table shows the GL entries for intra-state or intra-union territory purchases of services where service provider is unregistered.

| Particulars | Amount |
|--|--|
| **Service Account** | 10000 |
| **SGST/UTGST Receivable Account** | 900 |
| **CGST Receivable Account** | 900 |
| **Cash/Bank Account** | -10000 |
| **SGST/UTGST Payable Account** | -900 |
| **CGST Payable Account** | -900 |

### GL entries for inter-state purchase

For this example, the following table shows the GL entries for inter-state purchase of services where service provider is unregistered.
  
| Particulars | Amount |
|--|--|
| **Service Account** | 10000 |
| **Bank/Cash Account** | -10000 |
| **IGST Receivable Account** | 1800 |
| **IGST Payable Account** | -1800 |

<!--- GL Entries for Intra-state purchase of services where service provider is registered are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|
    |**CGST Receivable Account**|900|
    |**SGST/UTGST Receivable Account**|900|
    |**Cash/Bank Account**|-11800|  

> [!TIP]
> In case of Inter-State purchase of services IGST is applicable.-->

## Related information

[GST on Advance Payment to Vendor](GST-GST-on-Advance-Payment-made-to-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
