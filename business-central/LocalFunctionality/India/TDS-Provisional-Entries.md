---
title: TDS on Provisional Entries
description: Record provisional TDS entries and review the related transaction fields, processing steps, and accounting examples in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, provisional entries
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TDS on provisional entries

As per TDS rules, tax (TDS) has to be deducted at source, when amount is paid or credited to the account of the payee whichever is earlier. When the amount is credited to suspense account or any provisional account, then it's treated as amount is credited to the account of the payee and tax has to be deducted at source. Hence, Tax has to be deducted at source even on provisions made in the books of accounts to which TDS provisions are applicable.

A provisional entry should be posted before posting an actual entry, on posting of actual entry, provisional entry is reversed. As per requirement, TDS to be calculated on provisional entry and on posting of actual entry, system shouldn't calculate TDS as it is deducted in provisional entry.

For example, create and post a provisional expense journal for INR 10000 against professional expenses, with an illustrative TDS rate of 10%. This rate is an example assumption, not guidance on current tax law.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Purchase Journal**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**Posting Date**|Specify the date of entry.|  
    |**Document Type**|Select Invoice as document type.|
    |**Document No.**|Specify the document number.|
    |**Party Type**|Select Vendor as party type.|
    |**Party Code**|Select relevant vendor code.|
    |**Account Type**|Select G/L Account.| 
    |**Account No**|Select relevant account number for provision entry.|
    |**Amount**|Amount should be negative.|
    |**TDS Section**|Select relevant TDS Section.|
    |**Bal. Account Type**|Select G/L Account as balance account type.|
    |**Bal. Account No.**|Select the relevant expense account.|
    |**Provisional Entry**|Mark true.|

    In this case TDS calculation is as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|10000|  
    |**TDS Amount**|1000 (10000*10%)|

    GL Entries for Provisional Entry areas following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|10000|
    |**Provisional Account**|-10000|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|1000|

- Later invoice is created against the provisional entry.

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Purchase Journal**, and then choose the related link.
  1. Fill in the fields as described in the following table.

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**Posting Date**|Specify the date of entry.|  
    |**Document Type**|Select Invoice as document type.|
    |**Document No.**|Specify the document number.|
    |**Party Type**|Select Vendor as party type.|
    |**Party Code**|Select relevant vendor code.|
    |**Account Type**|Select Vendor.| 
    |**Account No**|Select relevant vendor code.|
    |**Amount**|Amount should be negative.|
    |**Bal. Account Type**|Select G/L Account as balance account type.|
    |**Bal. Account No.**|Select the relevant expense account.|

  1. Choose **Apply Provisional Entry** and select the relevant open provisional entry for the vendor.

     GL Entries for purchase invoice against provisional entry are as following:

     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Vendor Account**|-10000|
     |**Provisional Account**|10000|

  1. Post the invoice. The original provision is reversed without reversing the TDS already deducted. The provisional entry is closed, and **Applied Invoice No.** is updated with the invoice number.

- If this is found that the provisional entry needs to be reversed, then option of **Reverse Transaction** and **Reverse Without TDS** are available in Provisional Entries.

  - **Reverse Transaction**: Reverses the selected transaction, including TDS, subject to the reversal checks.
  - **Reverse Without TDS**: Reverses the provisional posting without reversing TDS. Use this action after the TDS has been paid. It isn't allowed while an unpaid TDS entry exists for the transaction.
  - **Reversed After TDS Paid**: Identifies a provisional entry reversed after payment of TDS.

> [!NOTE]
> Use a single journal line per document for a provisional entry or an invoice that applies a provisional entry. You can't apply a provisional entry that is closed, reversed, or marked **Reversed After TDS Paid**.

## Related information

[TDS Adjustment Entry](TDS-Adjustment-Entries.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
