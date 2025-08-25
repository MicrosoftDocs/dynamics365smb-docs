---
title: Report selection for finance reports in Business Central
description: Describes how to setup which financial report definitions should be used for the core finance reports such as Balance Sheet, Income Statement, and Retained Earnings.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 08/22/2025
ms.custom: bap-template
ms.search.keywords: bi, analysis, KPI, account schedule, financial report, Balance Sheet, Income Statement, and Retained Earnings
ms.search.form: 118, Report_151, Report_154, Report_155, Report_156, 
ms.service: dynamics-365-business-central
---

# Report selection for built-in finance reports

[!INCLUDE[prod_short](includes/prod_short.md)] provides built-in finance reports for Balance Sheet, Income Statement, Cash Flow, and Retained Earnings. These reports all use the **Financial Reporting** feature for defining the data and the layouts used. You can replace the standard layouts provided in [!INCLUDE[prod_short](includes/prod_short.md)] with your own.

## Built-in finance reports based on G/L account categories

Setting up financial reports requires an understanding of the structure of your chart of accounts. With the use of G/L account categories, you can simplify your financial report definitions and also make them more resilient to changes in the chart of accounts structure. The G/L account categories page also allows you to create financial report definitions for Balance Sheet, Income Statement, Cash Flow, and Retained Earnings.

Learn more at [Use G/L account categories to change the layout of your financial statements](bi-row-definitions.md#use-gl-account-categories-to-change-the-layout-of-your-financial-statements).


## Changing the foundation for the built-in finance reports

You can change the default financial reports used for the built-in finance reports Balance Sheet, Income Statement, Cash Flow, and Retained Earnings with your own report definitions. Navigate to the *General Ledger Setup* page and locate the *Reporting* section.

## Related information

[View a financial report](finance-financial-reporting-view-a-report.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
