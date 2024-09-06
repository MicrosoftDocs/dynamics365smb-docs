---
title: Organize report data using account categories
description: Learn how to categorize general ledger accounts for reporting purposes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 07/11/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 108, 490, 790
ms.service: dynamics-365-business-central
---

# Organize report data using account categories

The **G/L Account Categories** page lets you create simple financial reports based on your chart of accounts.  

By providing categories, subcategories, and account mapping to your chart of accounts, [!INCLUDE [prod_short](includes/prod_short.md)] includes basic financial reporting out of the box. If you're just getting started with financial reporting, the standard reports are excellent options until you become more established. 

## Use G/L account categories 

You create the first layer of a financial report by selecting an account category for each general ledger account. There are six categories:

* Assets
* Liabilities
* Equity
* Income
* Cost of Goods
* Expense

You specify categories on the **G/L Account Card** or **G/L Account Categories** pages. The purpose is to identify the major sections of primary financial reports, such as the Balance Sheet and Income Statement reports.  

## Use account subcategories

You can also create subcategories for each account. Subcategories help add more details to the mapping for accounts in each category. You also specify subcategories on the **G/L Account Card** or **G/L Account Categories** pages. The purpose is to identify the subsections of primary financial reports, such as the Balance Sheet and Income Statement reports. Subcategories are more flexible than categories because you can define them.  

## Map general ledger accounts

The most important feature of the out-of-the-box financial reports is mapping G/L accounts to categories. All accounts in the chart of accounts should be listed in a selected category and subcategory, so when you generate financial reports you include all mapped accounts.  

## Generate financial reports

After you set up categories and subcategories have and map all accounts on the chart of accounts, choose **Generate Financial Reports**. This action updates financial reports with the M- prefix with the mapping provided for your chart of accounts.  

To control which reports update when you generate financial reports, update the fields in the **Reporting** section of the **General Ledger Setup** page.  

You can remap and update these reports at any time. If you choose to regenerate them, you can choose to keep the original reports and create copies with the new mapping.

## See also

[Primary capabilities of financial reporting](finance-financial-reporting-capabilities.md)  
[Design your own financial reports](bi-design-financial-reports.md)
