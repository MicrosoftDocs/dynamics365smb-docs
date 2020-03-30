---
title: GIFI Codes in Canada | Microsoft Docs
Description: In Canada, you can set up General Index of Financial Information (GIFI) codes and assign them to posting accounts
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: local
ms.date: 04/01/2020
ms.author: SorenGP

---
# Work With GIFI Codes
Fiscal information can include general ledger accounts, reports, income statements, balance sheets, and statements of retained earnings. Fiscal information is classified using codes. The use of codes helps the government to process information, prepare for electronic filing, and validate tax information electronically. The use of codes also helps statistical organizations to work more efficiently, as financial information is more readily available. For more information, see the [Canada Revenue Agency website](https://www.cra-arc.gc.ca/).

The Canada Revenue Agency uses General Index of Financial Information (GIFI) codes to collect, validate, and process financial and tax information electronically. It is a best practice to assign GIFI codes only to posting accounts, so that all totaling is done by your tax preparation software.

When an account is associated with a GIFI code, it is reported to the revenue agency under that code. Multiple accounts can all have the same GIFI code, but each account can have only one GIFI code.

You can export balance information by GIFI code and save the exported file in Excel, which is useful for transferring information to your tax preparation software.

## To set up GIFI codes
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you must set up GIFI codes for general ledger accounts, reports, balance sheets, income sheets, and statements of retained earnings.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **GIFI Codes**, and then choose the related link.
2. On the **GIFI Codes** page, choose the **New** action.
3. Set up GIFI codes by filling the fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## To associate GIFI codes with G/L accounts
To report financial information by GIFI code, each GIFI code must be associated with the appropriate accounts in the chart of accounts.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.
2. Select a relevant general ledger account, and then choose the **Edit** action.
3. On the **Cost Accounting** FastTab, in the **GIFI Code** field, select an appropriate GIFI code.

## To view account balances using the GIFI code report
You can review your account balances by GIFI code by using the **Account Balances by GIFI Code** report.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Account Balances by GIFI Code**, and then choose the related link.
2. Specify what to include in the report by filling the fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. Choose the **Print** or the **Preview** button.

## To export balance information using GIFI codes
You can export balance information using GIFI codes and save the exported file in Excel. You can modify, save, or delete the file. You can use the file to transfer information to your tax preparation software.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export GIFI Info. to Excel**, and then choose the related link.
2. Specify what to export to Excel by filling the fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. Choose the **OK** button.

> [!NOTE]  
>   The Excel file has the following characteristics:

* The balance is rounded to the nearest percentage, but the cell value maintains the same percentage as it does in the general ledger.
* Negative numbers are represented as positive number in brackets. Accordingly, -123 is represented as (123).

## See Also
[Canada Local Functionality](canada-local-functionality.md)  
[Finance](../../finance.md)   
[Setting Up Finance](../../finance.md)
