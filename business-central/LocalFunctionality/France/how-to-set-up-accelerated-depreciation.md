---
title: Set Up Accelerated Depreciation
description: To use the accelerated depreciation calculation, you must set up depreciation books for fixed assets.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 5610, 5611
ms.date: 02/14/2022
ms.author: bholtorf

---
# Set Up Accelerated Depreciation

To use the accelerated depreciation calculation, you must set up the following depreciation books for fixed assets:  

- The accounting depreciation book (integrated with the general ledger).  
- The tax depreciation book (not integrated with the general ledger).  

> [!NOTE]  
> When you post an acquisition, depreciation, or disposal for the accounting depreciation book, the transaction is duplicated and posted in the tax depreciation book when the fixed asset journal is posted.  

The difference between the accounting depreciation book and the tax depreciation book is managed through the settings on the **Integration** FastTab on the deprecation book card as indicated in the following table.  

|Depreciation book purpose  |Value of the Derogatory field  |
|---------|---------|
|Accounting depreciation  | Switched on       |
|Tax depreciation     | Switched off |

The **Derogatory** field specifies if you want derogatory entries that are posted to this depreciation book to be posted both to the general ledger and the FA ledger. If you have placed a check mark in the field, you must use the FA G/L journal to post derogatory entries.

You specify the G/L accounts that must be used in the **FA Posting Group** page. In the **Depreciation Book** page, you specify the posting group that must be used.

If you do not place a check mark in the field, you must use the FA journal to post derogatory entries, which will be posted only to the FA Ledger Entry table.

For the tax depreciation book, on the **General** FastTab, you then specify the relevant accounting depreciation book in the **Derogatory Calculation** that will calculate derogatory depreciation. The **Used with Derogatory Book** field in the accounting depreciation book is updated with the tax depreciation book code.  

## Derogatory calculation

The **Derogatory Calculation** field on a depreciation book specifies if this book is used as tax depreciation book to calculate derogatory depreciation. The specified code for the accounting depreciation book establishes a derogatory setup.

As for the tax book, only FA entries will be posted, the check boxes on the **Integration** tab cannot be checked.

When the field is blank, [!INCLUDE[prod_short](../../includes/prod_short.md)] will use the depreciation book in a standard way. If it is not blank, the system will calculate derogatory depreciation.

## See Also

[Accelerated Depreciation](accelerated-depreciation.md)  
[Calculate Accelerated Depreciation](how-to-calculate-accelerated-depreciation.md)  
[Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]