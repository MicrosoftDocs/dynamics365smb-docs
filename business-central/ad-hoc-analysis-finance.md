---
title: Ad-hoc analysis of finance data
description: Learn how to use the data analysis mode to analyze finance data.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 20, 516, 9300, 5119, 9301, 9305
ms.date: 02/13/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of finance data

This article explains how to use the **Data Analysis** feature to analyze finance data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "Total assets over time", "Accounts Receivable", "Accounts Payable," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages to start doing ad-hoc analysis of finance processes:

- [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis)
- [G/L Registers](https://businesscentral.dynamics.com/?page=116&layout=analysis)
- [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis)
- [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis)

## Ad-hoc analysis scenarios in finance

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of finance scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
|[Example: Finance (Accounts Receivable)](#example-finance-accounts-receivable) | See what your customers owe you, for example, broken down into time intervals for when amounts are due. | [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis) | **Customer Name**, **Due Date**, and **Remaining Amount** |
| [Finance (Accounts Payable)](#example-finance-accounts-payable) | See what you owe your vendors, maybe broken down into time intervals for when amounts are due. | [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis) | **Vendor Name**, **Document Type**, **Document No.**, **Due Date Year**, **Due Date Month**, and **Remaining Amount**. |
| [Finance (Sales invoices by G/L account)](#example-finance-sales-invoices-by-gl-account) | See how your sales invoices distribute over G/L accounts from the chart of accounts, for example, broken down into time intervals for when amounts were posted. | [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis) | **G/L Account name**, **Source Code**, **G/L Account name**, **G/L Account No.**, **Debit Amount**, **Credit Amount**, **Posting Date Year**, **Posting Date Quarter**, and **Posting Date Month** |
| [Finance (Income statement)](#example-finance-income-statement) | See your income over the income accounts from the chart of accounts, for example, broken down into time intervals for when amounts were posted. | [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis) | **G/L Account No.**, **Posting Date**, and **Amount**. |
| [Finance (total assets)](#example-finance-total-assets) | See your assets over the asset accounts from the chart of account, for example, broken down into time intervals for when amounts were posted. | [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis) | **G/L Account No.**, **Posting Date**, and **Amount**. |
| [Finance (transaction overview)](#example-finance-transaction-overview) | Get an overview of the types of transactions that happpen to your general ledger and the types of sources for them.  | [G/L Registers](https://businesscentral.dynamics.com/?page=116&layout=analysis) | **Source code**. |


### Example: Finance (Accounts Receivable)

To see what your customers owe you, maybe broken down into time intervals for when amounts are due, follow these steps:

1. Open the [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the *Search* field on the right).
1. Turn on the **Pivot* Mode** toggle (located above the **Search** field on the right).
1. Drag the **Customer Name** field to the **Row Groups** area, and drag **Remaining Amount** to the **Values** area.
1. Drag the **Due Date Month** field to the **Column Labels** area.
1. To do the analysis for a given year or quarter, apply a filter in the **Analysis Filters** menu (located below the **Columns** menu on the right).
1. Rename your analysis tab to **Aged Accounts by Month**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-customer-ledger-entries-ar-example.png" alt-text="Example of how to do an AR data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-customer-ledger-entries-ar-example.png":::

### Example: Finance (Accounts Payable)

To see what you owe your vendors, maybe broken down into time intervals for when amounts are due, follow these steps:

1. Open the [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis) list page, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **Vendor Name**, **Document Type**, and **Document No.** fields to the **Row Groups** area, and then drag the **Remaining Amount** field to the **Values** area.
1. Drag the **Due Date Year** and **Due Date Month** fields to the **Column Labels** area. Drag the fields in that order.
1. To do the analysis for a given year or quarter, apply a filter in the **Analysis Filters** menu (located below the **Columns** menu on the right).
1. Rename your analysis tab to **Aged Payable Accounts by Month**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-vendor-ledger-entries.png" alt-text="Example of how to do data analysis on the Vendor Ledger Entries page." lightbox="media/data-analysis-vendor-ledger-entries.png":::

### Example: Finance (Sales invoices by G/L account)

To see how your sales invoices distribute over G/L accounts from the chart of accounts, for example, broken down into time intervals for when amounts were posted, follow these steps:

1. Open the [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) page.
1. Add the **G/L Account name** and **Source Code** fields by personalizing the page. On the **Settings** menu, choose **Personalize**.
1. Exit personalization mode.
1. Choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. On the **Analysis Filters** menu, set a filter on the **Source Code** field to **SALES**. If you have customizations that add other values, you can add those too.
1. On the **Columns** menu, remove all columns (select the box next to the **Search** field).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **G/L Account name** and **G/L Account No.** fields to the **Row Groups** area.
1. Drag the **Debit Amount** and **Credit Amount** fields to the **Values** area.
1. Drag the **Posting Date Year**, **Posting Date Quarter**, and **Posting Date Month** fields to the **Column Labels** area.
1. Rename your analysis tab to **Invoice breakdown by account**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-gl-entries-invoices.png" alt-text="Example of how to do data analysis on the G/L Ledger Entries page (to understand sales postings)." lightbox="media/data-analysis-gl-entries-invoices.png":::

### Example: Finance (Income statement)

To see your income over the income accounts from the chart of account, broken down into time intervals for when amounts were posted, follow these steps:

1. Open the [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis) list and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **G/L Account No.** field to the **Row Groups** area, and drag **Amount** to the **Values** area.
1. Drag the **Posting Date Month** field to the **Column Labels** area.
1. For the income statement, filter on the accounts you use. In the [!INCLUDE [prod_short](includes/prod_short.md)] demo data, these accounts start with "4", but your chart of accounts might be different. Set a filter on the accounts in the **Analysis Filters** menu (located below the **Columns** menu on the right).

   > [!TIP]
   > To see which accounts is used in your setup, run the [Trial Balance by Period](https://businesscentral.dynamics.com/?report=38) report.

1. Rename your analysis tab to **Income by Month**, or something that describes this analysis.

### Example: Finance (total assets)

To see your assets over the asset accounts from the chart of account, broken down into time intervals for when amounts were posted, do as follows:

1. Open the [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis) list and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **G/L Account No.** field to the **Row Groups** area, and drag **Amount** to the **Values** area.
1. Drag the **Posting Date Month** field to the **Column Labels** area.
1. For the total assets statement, filter on the accounts you use. In the [!INCLUDE [prod_short](includes/prod_short.md)] demo data, these accounts start with "10", but your chart of accounts might be different. Set a filter on appropriate accounts in the **Additional Filters** menu (located below the **Columns** menu on the right).

   > [!TIP]
   > To see which accounts are used in your setup, run the [Trial Balance by Period](https://businesscentral.dynamics.com/?report=38) report.

1. Rename your analysis tab to **Income by Month**, or something that describes this analysis.


### Example: Finance (transaction overview)

[!INCLUDE [gl-register-analysis-example](includes/gl-register-analysis-example.md)]


## Data foundation for ad-hoc analysis on finance

When you post journals, [!INCLUDE [prod_short](includes/prod_short.md)] creates entries in the **G/L Entry** table. Therefore, ad-hoc analysis on general finance is typically done on the [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) page. For accounts receivable and payable, you can analyze [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) and [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29), respectively.

Learn more in the following articles:

- [Data foundation for ad-hoc analysis on sales](ad-hoc-analysis-sales.md#data-foundation-for-ad-hoc-analysis-on-sales)
- [Data foundation for ad-hoc analysis on purchasing](ad-hoc-analysis-purchasing.md#data-foundation-for-ad-hoc-analysis-on-purchasing)
- [Analyze G/L entries](finance-how-to-analyze-gl-entries.md)

## See also

[Analyze G/L entries](finance-how-to-analyze-gl-entries.md)  
[Analyze list and query data with analysis mode](analysis-mode.md)  
[Financial analytics overview](bi.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Finance overview](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]