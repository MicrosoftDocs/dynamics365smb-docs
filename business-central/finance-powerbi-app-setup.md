---
title: Setup the Finance Power BI app
description: Learn how to setup the Power BI Finance app
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37059, 36984, 36985, 36986, 36987, 36988, 36989, 36990, 36991, 36992, 36993,36994, 36995, 36996, 36997
ms.date: 11/19/2024
ms.service: dynamics-365-business-central
---

# Setup the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)]

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article explains how to setup the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] in [!INCLUDE [prod_short](includes/prod_short.md)]. 

For the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] to show correct KPIs and reports, you need to do two things in [!INCLUDE [prod_short](includes/prod_short.md)]:

1. Setup G/L account categories for your chart of accounts. 
1. Map G/L account categories to corresponding categories used in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model.

## Prerequisites

Before configuring the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] for [!INCLUDE [prod_short](includes/prod_short.md)], you must have:

1. A connector (AL) app that contains APIs, setup pages, and embed pages. Connectors are preinstalled with [!INCLUDE [prod_short](includes/prod_short.md)].
1. Installed the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app that contains a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports for finance.
1. Run the **Connect to Power BI** assisted setup guide.

For more information, see [Install Power BI apps for Business Central](across-powerbi-install-business-central-apps.md).


## Configure date filtering for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] (semantic model)

This section describes how to configure the date filtering for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)]. The app can be configured to load data based on the **Start Date** and **End Date**. This filter helps improve performance of your [!INCLUDE [prod_short](includes/prod_short.md)] environment and reduce [!INCLUDE [powerbi-name](includes/powerbi-name.md)] load times by only loading the data you intend to analyze.

> [!NOTE]
> Configuring date filtering for the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] is optional and is designed to help manage large datasets.

The **Start Date** and **End Date** can be applied to the following tables:
- G/L Entries (related to the Income Statement)
- G/L Budget Entries
- Customer Ledger Entries
- Vendor Ledger Entries

**How to setup date filtering**

1. Search and open the **[Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951)** page.
1. Expand the **Finance Report** section in this page.
1. Set **Start Date** and **End Date** under the **Income Statement & G/L Budget Entry Filters** group.

Repeat steps 2-3 for the date setup under **Customer Ledger Entry Filters** and **Vendor Ledger Entry Filters**.

The following fields are available under the **Finance Report** fast tab:

|No.| Data Area | Field Name | Description |
|---| ---       | ---        | ---         |
|1  | Income Statement and G/L Budgets	   | Start Date      | Specifies the starting date to apply to a range of Income Statement G/L entries and G/L Budget entries.   |
|2  | Income Statement and G/L Budgets	   | End Date        | Specifies the end date to apply to a range of Income Statement G/L entries and G/L Budget entries.        |
|3  | Customer Ledger Entries	            | Start Date      | Specifies the starting date to apply to a range of Customer Ledger Entries.                               |  
|4  | Customer Ledger Entries	            | End Date        | Specifies the end date to apply to a range of Customer Ledger Entries.                                    |
|5  | Vendor Ledger Entries	            | Start Date      | Specifies the starting date to apply to a range of Vendor Ledger Entries.                                 |
|6  | Vendor Ledger Entries	            | End Date        | Specifies the end date to apply to a range of Vendor Ledger Entries.                                      |


## Setup G/L account categories for your chart of accounts

G/L account categories is a powerful tool to group general ledger accounts into categories and this is prerequisite for using the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance app. 

Specifically, for each posting account in the Chart of Accounts, you must set an **Account Category** and **Account Subcategory**. You do not need to set up the totalling accounts.

For more information on how to work with G/L account categories, see [G/L account categories](./finance-general-ledger.md#account-categories).

## Map G/L account categories to corresponding categories used in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model.

The [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance app has been setup with a default mapping of G/L account categories in [!INCLUDE [prod_short](includes/prod_short.md)] to corresponding values in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model. This mapping is needed for the finance KPIs and reports to show correct values. 

Below, you can see the default mapping of parameters in the Power BI Finance semantic model to the **G/L Account Categories** in Business Central. You can change the default values of the **Business Central Category** columns to your choice of G/L account categories by choosing the **Power BI Account Categories** action in the **Power BI Connector Setup** setup page or by navigating directly to the **Power BI Account Categories** page.

### Level 1 Categories

Level 1 categories are the top-level categories without any indentation.

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

| Power BI Account Category                        	| Business Central Category     	   |
|---	                                            |---	                              |
| Current Assets (Level 2 Category)                	| Current Assets                	   |
| Current Liabilities (Level 2 Category)           	| Current Liabilities           	   |
| Shareholder's Equity (Level 2 Category)          	| Common Stock                  	   |
| Interest Expense (Level 2 Category)             	| Interest Expense                  |
| Tax Expense (Level 2 Category)                   	| Tax Expense                   	   |
| Extraordinary Expense (Level 2 Category)         	| Extraordinary Expense             |
| FX Losses Expense (Level 2 Category)             	| FX Losses Expense                 |      	
| Depreciation and Amortization (Level 2 Category) 	| Depreciation and Amortization     |
| Interest Revenue (Level 2 Category)              	| Interest Income                	|
| FX Gains Revenue (Level 2 Category)              	| FX Gains Income                   |
| Extraordinary Revenue (Level 2 Category)         	| Extraordinary Income          	   |
| Fixed Assets (Level 2 Category)                  	| Fixed Assets                      |
| Payroll Liabilities (Level 2 Category)           	| Payroll Liabilities               |
| Longterm Liabilities (Level 2 Category)          	| Long Term Liabilities           	|


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



## Troubleshooting guide 

If you experience issues with the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)], maybe some of the sections below can help you get unblocked.

### Geeting the "Column ‘G/L Account No.’ in Table ‘G/L Account’ contains a duplicate value" error?

When refreshing data from your [!INCLUDE [prod_short](includes/prod_short.md)] environment into the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)], a refresh error may occur due to how your **Begin-Total** and **End-Total** accounts are configured in your **Chart of Accounts**. 

If you receive this error, please review the totalling accounts.

```
Something went wrong
There was an error when processing the data in the dataset.
Please try again later or contact support. If you contact support, please provide these details.

Data source error: Column 'G/L Account No.' in Table 'G/L Account' contains a duplicate value 'X' and this is not allowed for columns on the one side of a many-to-one relationship or for columns that are used as the primary key of a table.
```

**Why does this happen?**

This is due to the Finance Connector app relying on the totalling accounts for hierarchy and indentation purposes.

Your totalling for an **End-Total** account must exactly reference both the **Begin-Total** and **End-Total** accounts. This means one **Begin-Total** account can only be used in one **End-Total** account.

**Fixing the totalling on your G/L Accounts**

The totalling accounts should be set up such as the following example:

1. A Begin-Total account of **1300 (Vehicles)** and the End-Total account of **1390 (Vehicles, Total)**.
2. The totalling defined on the End-Total is **1300..1390**. 
3. If your totalling account is defined as any other combination (such as 1300..1340, 1310..1390, or 1310..1340, etc.), this will cause the error.
4. One **Begin-Total** account can only be used in one **End-Total** account. If you use a **Begin-Total** account in two or more **End-Total** accounts, then the Finance Power BI app cannot match it to an **End-Total** account.


## See also

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)   
[Power BI finance app](finance-powerbi-app.md)   
[Financial analytics overview](bi.md)  
[Finance overview](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]