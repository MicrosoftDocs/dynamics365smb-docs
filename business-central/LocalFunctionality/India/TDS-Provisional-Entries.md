---
title: TDS on Provisional Entries
description: Learn how TDS is applied to provisional entries in Business Central India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, provisional entries
ms.date: 06/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# TDS on provisional entries

As per TDS rules, tax (TDS) has to be deducted at source, when amount is paid or credited to the account of the payee whichever is earlier. When the amount is credited to suspense account or any provisional account, then it's treated as amount is credited to the account of the payee and tax has to be deducted at source. Hence, Tax has to be deducted at source even on provisions made in the books of accounts to which TDS provisions are applicable.

A provisional entry should be posted before posting an actual entry, on posting of actual entry, provisional entry is reversed. As per requirement, TDS to be calculated on provisional entry and on posting of actual entry, system shouldn't calculate TDS as it is deducted in provisional entry.

For example, provisional expense journal has to be created and posted for INR 10000 against professional expense and 10% TDS to be calculated on the expense amount.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Journal**, and then choose the related link.
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
    |**Bal. Account No.**|Select the relevant expanse account.|
    |**Provisional Entry**|Mark true.|

    In this case TDS calculation is as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|10000|  
    |**TDS Amount**|1000 (10000*1%)|

    GL Entries for Provisional Entry areas following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|10000|
    |**Provisional Account**|-10000|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|1000|

- Later invoice is created against the provisional entry.

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Journal**, and then choose the related link.
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
    |**Bal. Account No.**|Select the relevant expanse account.|

  1. Select Apply Provisional Entry and select the relevant provision entry posted for the vendor.

     GL Entries for purchase invoice against provisional entry are as following:

     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Vendor Account**|-10000|
     |**Provisional Account**|10000|

  1. On posting of provisional entry Provisional Entries are created, and once the invoice is applied with the entry Applied Invoice No. field is updated with the invoice number.

- If this is found that the provisional entry needs to be reversed, then option of **Reverse Transaction** and **Reverse Without TDS** are available in Provisional Entries.

  1. Reverse Transaction reverses all the posted entries of the selected transaction.
  1. Reverse Without TDS reverses all the posted entries of the selected transaction other than the TDS entry.
  1. System marks the reverse transaction as **Reversed After TDS Paid** if TDS is paid to the government for the selected transaction.

## Related information

[TDS Adjustment Entry](TDS-Adjustment-Entries.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
