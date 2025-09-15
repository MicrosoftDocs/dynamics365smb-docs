---
title: Set up the Finance Power BI app
description: Learn how to set up the Power BI Finance app
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: reporting
ms.search.form: 36961_Primary, 37059, 36984, 36985, 36986, 36987, 36988, 36989, 36990, 36991, 36992, 36993,36994, 36995, 36996, 36997
ms.date: 06/11/2025
ms.service: dynamics-365-business-central
---

# Set up the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)]

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article explains how to set up the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] in [!INCLUDE [prod_short](includes/prod_short.md)].

For the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] to show correct KPIs and reports, do two things in [!INCLUDE [prod_short](includes/prod_short.md)]:

1. Set up G/L account categories for your chart of accounts.
1. Map G/L account categories to corresponding categories used in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model.

## Prerequisites

Before you configure the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] for [!INCLUDE [prod_short](includes/prod_short.md)], you must:

1. Have a connector (AL) app that contains APIs, setup pages, and embed pages. Connectors are preinstalled with [!INCLUDE [prod_short](includes/prod_short.md)].
1. Install the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app that contains a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports for finance.
1. Run the **Connect to Power BI** assisted setup guide.

To learn more, go to [Install Power BI apps for Business Central](across-powerbi-install-business-central-apps.md).

## Configure date filtering for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] semantic model

This section describes how to configure date filtering for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)]. You can configure the app to load data based on the **Start Date** and **End Date**. This filter helps improve performance in your [!INCLUDE [prod_short](includes/prod_short.md)] environment and reduce [!INCLUDE [powerbi-name](includes/powerbi-name.md)] load times by only loading the data you intend to analyze.

> [!NOTE]
> Configuring date filtering for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] is optional, and is designed to help manage large datasets.

The **Start Date** and **End Date** filter can apply to the following tables:

- G/L Entries (related to the Income Statement)
- G/L Budget Entries
- Customer Ledger Entries
- Vendor Ledger Entries

### Set up date filtering

1. Search and open the **[Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951)** page.
1. Expand the **Finance Report** section.
1. Fill in the **Start Date** and **End Date** fields under **Income Statement & G/L Budget Entry Filters**.

Repeat steps 2-3 for the date setup under **Customer Ledger Entry Filters** and **Vendor Ledger Entry Filters**.

The following fields are available on the **Finance Report** FastTab:

|No.| Data Area | Field Name | Description |
|---| ---       | ---        | ---         |
|1  | Income Statement and G/L Budgets   | Start Date      | Specifies the starting date to apply to a range of income statement G/L entries and G/L budget entries.   |
|2  | Income Statement and G/L Budgets   | End Date        | Specifies the end date to apply to a range of income statement G/L entries and G/L budget entries.        |
|3  | Customer Ledger Entries            | Start Date      | Specifies the starting date to apply to a range of customer ledger entries.                               |  
|4  | Customer Ledger Entries            | End Date        | Specifies the end date to apply to a range of customer ledger entries.                                    |
|5  | Vendor Ledger Entries            | Start Date      | Specifies the starting date to apply to a range of vendor ledger entries.                                 |
|6  | Vendor Ledger Entries            | End Date        | Specifies the end date to apply to a range of vendor ledger entries.                                      |

## Set up G/L account categories for your chart of accounts

G/L account categories are groups of general ledger accounts. The categories are required for using the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance app.

For each posting account in your chart of accounts, you must specify an **Account Category** and **Account Subcategory**. You don't need to set up the totaling accounts.

To learn more about how to work with G/L account categories, go to [G/L account categories](./finance-general-ledger.md#account-categories).

## Map G/L account categories to corresponding categories used in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model

The [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance app has default mappings for G/L account categories in [!INCLUDE [prod_short](includes/prod_short.md)] to corresponding values in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model. This mapping enables the finance KPIs and reports to show correct values.

The following sections show the default mappings. You can change the default values of the **Business Central Category** columns to your choice of G/L account categories by choosing the **Power BI Account Categories** action on the **Power BI Connector Setup** setup page or directly on the **Power BI Account Categories** page.

### Level 1 Categories

Level 1 categories are the top-level categories without indentation.

| Power BI Account Category                 | Business Central Category |
| ---                                       | ---                       |
| Assets (Level 1 Category)                 | Assets                    |
| Liabilities (Level 1 Category)            | Liabilities               |
| Equity (Level 1 Category)                 | Equity                    |
| Revenue (Level 1 Category)                | Income                    |
| Cost of Goods Sold (Level 1 Category)     | Cost of Goods Sold        |
| Expense (Level 1 Category)                | Expense                   |

### Level 2 Categories

Level 2 categories are the second-level categories with indentation.

| Power BI Account Category	| Business Central Category     |
|---                    |---                              |
| Current Assets (Level 2 Category) | Current Assets   |
| Current Liabilities (Level 2 Category)  | Current Liabilities   |
| Shareholder's Equity (Level 2 Category) | Common Stock          |
| Interest Expense (Level 2 Category)     | Interest Expense      |
| Tax Expense (Level 2 Category)          | Tax Expense            |
| Extraordinary Expense (Level 2 Category) | Extraordinary Expense |
| FX Losses Expense (Level 2 Category)     | FX Losses Expense  |
| Depreciation and Amortization (Level 2 Category) 	| Depreciation and Amortization     |
| Interest Revenue (Level 2 Category)  | Interest Income        |
| FX Gains Revenue (Level 2 Category)  | FX Gains Income         |
| Extraordinary Revenue (Level 2 Category) | Extraordinary Income   |
| Fixed Assets (Level 2 Category)          | Fixed Assets           |
| Payroll Liabilities (Level 2 Category)   | Payroll Liabilities     |
| Long-term Liabilities (Level 2 Category)  | Long Term Liabilities   |

### Level 3 Categories

Level 3 categories are the subcategories of Level 2 with indentation.

| Power BI Account Category                 | Business Central Category |
| ---                                       | ---                       |
| Inventory (Level 3 Category)              | Inventory                 |
| Accounts Payable (Level 3 Category)       | Accounts Payable          |
| Accounts Receivable (Level 3 Category)    | Accounts Receivable       |
| Purchases (Level 3 Category)              | Purchases                 |
| Purchase Prepayments (Level 3 Category)   | Prepaid Expenses          |
| Liquid Assets (Level 3 Category)          | Cash                      |

## Troubleshooting

If you experience issues with the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)], the information in the following sections might help you get unblocked.

### Getting the "[Unable to combine data] Section1/G\/L Entries/Combine Queries references other queries or steps, so it may not directly access a data source. Please rebuild this data combination." error?

When you install the Power BI app for Finance, make sure that you set the **Privacy level setting for this data source** field to **Organizational** when you authenticate.

:::image type="content" source="media/powerbi/power-bi-install-app-authenticate.png" alt-text="Screenshot of the Power BI app installer." lightbox="media/powerbi/power-bi-install-app-authenticate.png":::

### Getting the "Column Entry No. in Table G/L Entries contains a duplicate value" error?

When you refresh data from your [!INCLUDE [prod_short](includes/prod_short.md)] environment into the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)], a refresh error might happen with the following error message:

```
Something went wrong
There was an error when processing the data in the dataset.
Please try again later or contact support. If you contact support, please provide these details.

Data source error: Column '<oii>Entry No.</oii>' in Table '<oii>G/L Entries</oii>' contains a duplicate value
```

> [!NOTE]
> The cause of this error is a bug in the semantic model for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)].

This error indicates that there are duplicate G/L entries in the Finance fact table in the semantic model. The error displays when we attempt to combine the three subqueries (Balance Sheet G/L Entries, Income Statement G/L Entries, and Close Income Statement G/L Entries) into the single G/L Entries Fact table.

The current Balance Sheet G/L Entries query has a hard-coded filter transformation. This filter assumes that the source code for closing entries is CLSINCOME. This leads the model to allow closing entries to exist in both the Balance Sheet query and the Closing Entries query, resulting in duplicate entries.

### Getting the "Column ‘G/L Account No.’ in Table ‘G/L Account’ contains a duplicate value" error?

When you refresh data from your [!INCLUDE [prod_short](includes/prod_short.md)] environment into the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)], a refresh error might happen due to how your **Begin-Total** and **End-Total** accounts are configured in your **Chart of Accounts**.

```
Something went wrong
There was an error when processing the data in the dataset.
Please try again later or contact support. If you contact support, please provide these details.

Data source error: Column 'G/L Account No.' in Table 'G/L Account' contains a duplicate value 'X' and this is not allowed for columns on the one side of a many-to-one relationship or for columns that are used as the primary key of a table.
```

If you receive this error, you need to [identify the duplicate accounts in Business Central](#how-to-identify-the-duplicate-accounts-in-business-central), then apply the suggested changes.

#### Why did this error happen?

This error can happen because the Finance Connector app relies on the totaling accounts for hierarchy and indentation purposes.

Your totaling for an **End-Total** account must exactly reference both the **Begin-Total** and **End-Total** accounts.

> [!NOTE]
> You can only use one **Begin-Total** account in one **End-Total** account.

#### How to identify the duplicate accounts in Business Central

Power BI presents the first instance of a duplicate account in the error message. You might need to resolve multiple totaling accounts in sequence to resolve all duplicates.

In the following example, Power BI identifies account **1001** as having a duplicate value in the G/L Account table in the Semantic Model.

:::image type="content" source="media/powerbi/finance/duplicate-accounts-error-example.png" alt-text="Screenshot of the duplicate accounts error" lightbox="media/powerbi/finance/duplicate-accounts-error-example.png":::

##### Steps to follow in Business Central

1. Go to your chart of accounts.
1. Filter the list by **Totaling**, and filter by the account number mentioned in the error message. The filter should include asterisks before and after the account number. For example, *1001*.
1. Identify all end-total accounts that reference the duplicate account in the **Totaling** column.
1. [Fix the totaling on your G/L Accounts](#fix-the-totalling-on-your-gl-accounts).

:::image type="content" source="media/powerbi/finance/duplicate-totalling-accounts-example.png" alt-text="Screenshot of the duplicate totalling accounts structure" lightbox="media/powerbi/finance/duplicate-totalling-accounts-example.png":::

#### Fix the totaling on your G/L Accounts

Sometimes, the issue is due to incorrect account references in the **Totaling** column. Typically, removing duplicate account references fixes the problem.

For more complex situations, you might need to introduce new begin-total accounts to better organize your end-totals. Adding new accounts requires restructuring your chart of accounts.

The following example illustrates the recommended approach for setting up totaling accounts.

1. A **Begin-Total** account of **1300 (Vehicles)** and the **End-Total** account of **1390 (Vehicles, Total)**.
2. The totaling defined for the **End-Total** is **1300..1390**. Any other combination for your totaling account (such as 1300..1340, 1310..1390, or 1310..1340, etc.) can cause the error.

> [!NOTE]
> You can only use one **Begin-Total** account in one **End-Total** account. If you use a **Begin-Total** account in two or more **End-Total** accounts, the [!INCLUDE [power-bi-finance-app-name](includes/power-bi-finance-app-name.md)] can't match it to an **End-Total** account.

:::image type="content" source="media/powerbi/finance/recommended-totalling-structure-for-power-bi-reporting.png" alt-text="Screenshot of the recommended totalling structure for power bi finance reporting" lightbox="media/powerbi/finance/recommended-totalling-structure-for-power-bi-reporting.png":::

## Related information

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)  
[Power BI finance app](finance-powerbi-app.md)  
[Financial analytics overview](bi.md)  
[Finance overview](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
