---
title: GIFI Codes in Canada
description: In Canada, you can set up General Index of Financial Information (GIFI) codes and assign them to posting accounts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: local, GIFI, posting accounts
ms.search.form: 10017
ms.date: 02/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Work with GIFI codes in the Canadian version

Fiscal information can include general ledger accounts, reports, income statements, balance sheets, and statements of retained earnings. Fiscal information is classified using codes. The use of codes helps the government to process information, prepare for electronic filing, and validate tax information electronically. The use of codes also helps statistical organizations to work more efficiently, as financial information is more readily available. For more information, see the [Canada Revenue Agency website](https://www.cra-arc.gc.ca/).

The Canada Revenue Agency uses General Index of Financial Information (GIFI) codes to collect, validate, and process financial and tax information electronically. It is a best practice to assign GIFI codes only to posting accounts, so that all totaling is done by your tax preparation software.

When an account is associated with a GIFI code, it is reported to the revenue agency under that code. Multiple accounts can all have the same GIFI code, but each account can have only one GIFI code.

You can export balance information by GIFI code and save the exported file in Excel, which is useful for transferring information to your tax preparation software.

## Set up GIFI codes

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you must set up GIFI codes for general ledger accounts, reports, balance sheets, income sheets, and statements of retained earnings.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **GIFI Codes**, and then choose the related link.
1. On the **GIFI Codes** page, choose the **New** action.
1. Set up GIFI codes by filling the fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## Associate GIFI codes with G/L accounts

To report financial information by GIFI code, each GIFI code must be associated with the appropriate accounts in the chart of accounts.

1. Choose the ![Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.
1. Select a relevant general ledger account, and then choose the **Edit** action.
1. On the **Cost Accounting** FastTab, in the **GIFI Code** field, select an appropriate GIFI code.

## View account balances using the GIFI code report

You can review your account balances by GIFI code by using the **Account Balances by GIFI Code** report.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Balances by GIFI Code**, and then choose the related link.
1. Specify what to include in the report by filling the fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Choose the **Print** or the **Preview** button.

## Export balance information using GIFI codes

You can export balance information using GIFI codes and save the exported file in Excel. You can modify, save, or delete the file. You can use the file to transfer information to your tax preparation software.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export GIFI Info. to Excel**, and then choose the related link.
1. Specify what to export to Excel by filling the fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Choose the **OK** button.

> [!NOTE]  
> The Excel file has the following characteristics:

* The balance is rounded to the nearest percentage, but the cell value maintains the same percentage as it does in the general ledger.
* Negative numbers are represented as positive number in brackets. Accordingly, -123 is represented as (123).

## Related information

- [Canada Local Functionality](canada-local-functionality.md)  
- [Finance](../../finance.md)
- [Setting Up Finance](../../finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
