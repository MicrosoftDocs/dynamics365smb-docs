---
title: Sustainability financial reporting
description: Describes how to use financial reports to create various views and reports for analyzing sustainability performance data.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: reporting
ms.search.form: 104, 108, 490
ms.date: 10/24/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Analyzing sustainability entries with financial reports

The *financial reports* feature gives you insights into the financial data shown on your chart of accounts (COA). You can set up financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. But you can also analyze statistical and sustainability data with the same feature, and even combine all three types of data.  

## Prerequisites for financial reporting  

Setting up financial reports requires an understanding of the structure of the data you want to analyze. There are some key concepts that you likely need to pay attention to before you design your financial reports:

1. Related to the chart of accounts:

   1. Map G/L posting accounts to G/L account categories.
   2. Design how you use dimensions.
   3. Set up G/L budgets.  

2. Related to sustainability:

   1. Set up your sustainability accounts.
   2. Set up your carbon fees and CO2e in the **Emission Fees**.
   3. Design how you use dimensions.  

3. Related to the statistical accounts:

   1. Set up your statistical accounts.
   2. Design how you use dimensions.  

> [!NOTE]
> Financial reports doesn't work directly with CO2, CH4, or N2O emissions. Instead, it uses the CO2 equivalent model and that means you must first configure **CO2e** (carbon-dioxide equivalent) on the **Emission Fees** page.  

> [!NOTE]
> More details about using financial reports with financial data and chart of accounts can be found at [Prepare financial reporting with financial data and account categories](bi-how-work-account-schedule.md).

## Create a new financial report  

To quickly create your own financial reports, start by copying an existing one, as described in step 3 here:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.  
2. On the **Financial Reports** page, choose the **New** action to create a new financial report name.  
3. Fill in the report short name in **Name** field (you can't change the name later) and enter a **Description**.  
4. Choose a row definition and a column definition.
5. Choose the **Edit Report Definition** action to access more properties on the financial report.  
6. On the **Options** FastTab, you can edit the report description, change the row and column definitions, and define how to show dates. Dates can be a Day/Week/Month/Quarter/Year hierarchy, or use accounting periods. To learn more, go to [Comparing accounting periods using period formulas](bi-column-definitions.md#comparing-accounting-periods-using-period-formulas).
7. On the **Dimensions** FastTab, you can define dimension filters for the report.  
8. You can preview the report in the area below the **Dimensions** FastTab.

If you want to analyze your sustainability or statistical data, you can achieve this by setting up the **Row Definition**.  

To create or edit a row definition, follow these steps:

1. On the **Financial Reports** page, select the relevant financial report, and then choose the **Edit Row Definition** action.
2. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

> [!NOTE]
> The **Row No.** field shows the first 10 characters of an identifier, such as an account number. If you add elements with identifiers that start with the same 10 characters, you'll have duplicates in the **Row No.** field. If needed, you can manually edit the identifiers after you insert the elements. The full identifiers are displayed in the **Totaling** field.

> [!NOTE]
> You can combine all **Totaling Types**, that is, Posting accounts, Sust. Accounts, and Statistical Account.

> [!NOTE]
> Row definitions aren't versioned. When you change a row definition, the old version is replaced and your changes will be saved to the database.

### Analyzing sustainability data  

1. Enter the **Row No.** to identify your row and add **Description** as a text that will appear on the financial report line.
2. In the **Totaling Type** column, choose the **Sust. Accounts** option.
3. In the **Totaling** field, choose one or more sustainability accounts using all applicable filters.
4. In the **Amount Type** choose one of the options:
   1. Choose **CO2e** if you want to report CO2 equivalent value from the **CO2e Emission** field in the **Sustainability Ledger Entries**.
   2. Choose **Carbon Fee** if you want to report financial equivalent (carbon fee) from the **Carbon Fee** field on the **Sustainability Ledger Entries**.

5. If you choose **Formula** as a **Totaling Type**, you can use mathematical formulas in the **Totaling** column.  

### Analyzing statistical data

1. Enter the **Row No.** to identify your row and add **Description** as a text that will appear on the financial report line.
2. In the **Totaling Type** column, choose the **Statistical Accounts** option.
3. In the **Totaling** field, choose one or more sustainability accounts using all applicable filters.
4. If you choose **Formula** as a **Totaling Type**, you can use mathematical formulas in the **Totaling** column.  

## Related information

[Sustainability Management Overview](finance-manage-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)  
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Row definitions in Financial Reporting](bi-row-definitions.md)  
[Column definitions in Financial Reporting](bi-column-definitions.md)  
[Financial management](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
