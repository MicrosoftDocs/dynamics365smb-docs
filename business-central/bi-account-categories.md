---
title: Organize report data using account categories
description: Learn how to categorize general ledger accounts for reporting purposes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/06/2025
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 108, 490, 790_Primary
ms.service: dynamics-365-business-central
---

# Organize general ledger (G/L) data using account categories

The **G/L Account Categories** page lets you create simple financial reports based on your chart of accounts.  

By providing categories, subcategories, and account mapping to your chart of accounts, [!INCLUDE [prod_short](includes/prod_short.md)] includes basic financial reporting out of the box. If you're just getting started with financial reporting, the standard reports are excellent options until you become more experienced.

## Use G/L account categories

You create the first layer of a financial report by selecting an account category for each general ledger account. There are six categories:

* Assets
* Liabilities
* Equity
* Income
* Cost of Goods
* Expense

You specify categories on the **G/L Account Card** or **G/L Account Categories** pages. The purpose is to identify the major sections of primary financial reports, such as the Balance Sheet and Income Statement reports.  

:::image type="content" source="media/account categories financial reporting.png" alt-text="Shows the G/L account categories page.":::

## Use account subcategories

You can also create subcategories for each account. Subcategories help add more details to the mapping for accounts in each category. You also specify subcategories on the **G/L Account Card** or **G/L Account Categories** pages. The purpose is to identify the subsections of primary financial reports, such as the Balance Sheet and Income Statement reports. Subcategories are more flexible than categories because you can define them. 

:::image type="content" source="media/account subcategories.png" alt-text="Shows account subcategories."::: 

## Map general ledger accounts

The most important feature of the financial reports that [!INCLUDE [prod_short](includes/prod_short.md)] provides is the mapping between G/L accounts and account categories on the **G/L Account Categories** page. All accounts in the chart of accounts should be listed in a selected category and subcategory, so when you generate financial reports you include all mapped accounts. To learn more about mapping categories, go to the examples in [Walkthrough: Create custom financial reports](bi-examples-custom-financial-reports.md).  

:::image type="content" source="media/account mapping.png" alt-text="Shows accounts mapped to G/L account categories.":::

> [!NOTE]
> In 2024 release wave 1, [!INCLUDE [prod_short](includes/prod_short.md)] provides the mapping only in the United States. If you're using another country version, you must create the mapping yourself. The mapping will become available in more country versions in future releases.

## Generate financial reports

After you set up categories and subcategories have and map all accounts on the chart of accounts, choose **Generate Financial Reports**. This action updates financial reports with the M- prefix with the mapping provided for your chart of accounts.  

To control which reports update when you generate financial reports, update the fields in the **Reporting** section of the **General Ledger Setup** page.  

You can remap and update these reports at any time. If you choose to regenerate them, you can choose to keep the original reports and create copies with the new mapping.

## Audit changes to account categories

You can use the Change Log feature to capture changes users make to your G/L account categories. [!INCLUDE [include-audit-what-who-when](includes/include-audit-what-who-when.md)] 

The following table lists the table for G/L account categories and its ID.

| Table | Table ID |
| ----- | -------- |
| G/L Account Category | 570 |

[!INCLUDE [include-audit-changes-to-setup-learn-more-link](includes/include-audit-changes-to-setup-learn-more-link.md)]

## Related information

[Primary capabilities of financial reporting](finance-financial-reporting-capabilities.md)  
[Design your own financial reports](bi-design-financial-reports.md)  
[Financial analytics](bi.md)  
[Prepare financial reporting with financial data and account categories](bi-how-work-account-schedule.md)  
[Design your own financial reports](bi-design-financial-reports.md)  
[Walkthrough: Create custom financial reports](bi-examples-custom-financial-reports.md)  
