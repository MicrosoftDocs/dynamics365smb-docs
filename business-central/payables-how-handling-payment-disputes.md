---
title: Handle vendor payment disputes
description: Learn how to handle vendor payment disputes.
author: kennieNP
ms.topic: concept-article
ms.devlang: al
ms.search.keywords:
ms.search.form: Report_319
ms.date: 12/14/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Handle vendor payment disputes

You can mark a vendor ledger entry as **On hold** if there's a dispute about a supplier document. The on hold status helps you maintain transparency and efficiency while you manage and resolve the issue.

## To set a vendor ledger entry on hold

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendor ledger entries**, and then choose the related link.
2. Select the entry that you want to mark.
3. Choose **Edit List**. You can now enter up to 3 characters (likely your initials) in the **On Hold** field to indicate the document is on hold. 

## On hold entries, and the Suggest Vendor Payments batch job

The **Suggest Vendor Payments** batch job excludes vendor ledger entries that are **On Hold**. To learn more, go to [Suggest vendor payments](payables-how-suggest-vendor-payments.md).


## Analyzing On hold vendor ledger entries 

There are multiple other options for analyzing entries on hold. 

For instance, on the **Vendor ledger entries** page you can set a filter on the **On Hold** field to this value
``` Filter
<>''
```


You can also take the vendor ledger entries list page into analysis mode and define an analysis tab. To learn more, go to
[Using data analysis to show vendor ledger entries on hold](ad-hoc-analysis-purchasing.md#example-finance-accounts-payable---vendor-ledger-entries-on-hold)


Or you can run the [Payments on Hold](reports/report-319.md) report.

## Block vendors

You can also block a vendor, for example because of insolvency, so that people can't select the vendor for purchase documents, or so that they can't post payments to the vendor.

To learn more, go to [Block vendors](payables-how-block-vendors.md).

## Related information

[Using data analysis to show vendor ledger entries on hold](ad-hoc-analysis-purchasing.md#example-finance-accounts-payable---vendor-ledger-entries-on-hold)  
[Payments on Hold (report)](reports/report-319.md)  
[Suggest vendor payments](payables-how-suggest-vendor-payments.md)  
[Block vendors](payables-how-block-vendors.md)  
[Managing Payables](payables-manage-payables.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]