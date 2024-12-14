---
title: Handling vendor payment disputes
description: Read about how to hande vendor payment disputes
author: kennieNP
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.search.form: 27
ms.date: 12/14/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Handling vendor payment disputes

You can mark a vendor ledger entry *On hold* if there is a dispute about a supplier document. This allows for maintaining transparency and efficiency when you handle vendor disputes, so that your employees can effectively manage and resolve issues.

## To mark a vendor ledger entry On hold

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor ledger entries**, and then choose the related link.
2. Select the entry that you want to mark.
3. Choose **Edit List**. You can now enter up to 3 characters (likely your initials) in the **On Hold** field to indicate the document is on hold. 

## On hold entries and the Suggest Vendor Payments batch job

The **Suggest Vendor Payments** batch job excludes vendor ledger entries that are **On Hold**. To learn more, go to [Suggest vendor payments](payables-how-suggest-vendor-payments.md).


## Analyzing vendor ledger entry On hold

There are multiple other options for analyzing entries on hold. 

For instance, you can set filter the On Hold field on the vendor ledger entries list page to *<>''*.

You can also take the vendor ledger entries list page into analysis mode and define an analysis tab. To learn more, go to
[Using data analysis to show vendor ledger entries on hold](ad-hoc-analysis-purchasing.md#example-finance-accounts-payable---vendor-ledger-entries-on-hold)

Or you can run the [Payments on Hold](reports/report-319.md) report.


## Learn more

[Using data analysis to show vendor ledger entries on hold](ad-hoc-analysis-purchasing.md#example-finance-accounts-payable---vendor-ledger-entries-on-hold)  
[Payments on Hold (report)](reports/report-319.md)  
[Suggest vendor payments](payables-how-suggest-vendor-payments.md)  
[Managing Payables](payables-manage-payables.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]