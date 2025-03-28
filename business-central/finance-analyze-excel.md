---
title: Work with financial overviews in Excel (legacy)
description: Learn about how you can open the financial statements in Microsoft Excel from Business Central for better analysis.
author: brentholtorf
ms.topic: overview
ms.search.keywords: accountant, accounting, financial report
ms.search.form: 9027,
ms.date: 02/13/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Analyzing financial statements in Microsoft Excel (obsolete)

> [!NOTE]
> This feature is deprecated and will be removed in a later [!INCLUDE [prod_short](includes/prod_short.md)] release. Learn more in [Deprecated features in the base app](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1). Learn more about alternative finance reporting in [Financial analytics overview](bi.md).

[!INCLUDE [prod_short](includes/prod_short.md)] provides KPIs and get overviews of your company's finances. The following are examples of ways to analyze KPIs and overviews in Excel:

* Open lists in Excel and analyze the data.
* Export heavy financial statements such as your balance sheet or income statement to Excel, analyze the data, and print the reports.  

> [!TIP]
> By default, the reports you can view in Excel are designed to help you analyze the current year. The Income Statement report is an exception, however. That report lets you filter the data to include previous years in your analyses.

## Get the overview and the details in Excel

In the Business Manager and Accountant Role Centers, the **Reports** action lets you choose the financial statements to view in Excel. When you choose a statement, it will be opened in Excel or Excel Online. An add-in connects the data to [!INCLUDE [prod_short](includes/prod_short.md)]. However, you have to sign in with the same account that you use with [!INCLUDE [prod_short](includes/prod_short.md)]. The following table lists the reports and where they're available.  

|Report  |Role Center  |
|---------|---------|
|Balance Sheet                 | Business Manager, Accountant |
|Income Statement              | Business Manager, Accountant |
|Statement of Cash Flows       | Business Manager, Accountant |
|Statement of Retained Earnings| Business Manager, Accountant |
|Sales Taxes Collected         | Business Manager, Accountant |
|Customer Statements           | Business Manager, Accountant |
|Aged Accounts Payable         | Accountant |
|Aged Accounts Receivable      | Accountant |

Let's say you want to dig deeper into your cash flow. From the Business Manager or Accountant Role Center, you can open the **Statement of Cash Flows** report in Excel, but what actually happens is that we export the relevant data for you and create an Excel workbook based on a predefined template. Depending on your browser, you might be prompted to open or save the workbook.  

In Excel, you see a tab where the data is laid out for you on the first worksheet. All the data that was exported is also present in other worksheets in case you need it. You can print the report right away, or you can modify it until you have the overview and the details that you want. Use the [!INCLUDE [prod_short](includes/prod_short.md)] Excel Add-in to further filter and analyze data.  

### Understand the Excel templates

The predefined Excel reports are based on the data in the current company. For example, the demonstration company has set up the chart of accounts to list three cash accounts under *Current Assets*: 10100 **Checking account**, 10200 **Saving account**, and 10300 **Petty Cash**. The accounts have the **Account Subcategory** field set to *Cash*, and it's their combined amount that shows up as *Cash* in the **Balance Sheet** Excel report.  

Other sheets in the Excel workbook show the data behind the report. To find out what's behind the groupings in the Excel reports, you might have to filter the lists in [!INCLUDE [prod_short](includes/prod_short.md)].  

## The [!INCLUDE [prod_short](includes/prod_short.md)] Excel add-in

Your [!INCLUDE [prod_short](includes/prod_short.md)] experience includes an add-in for Excel. Depending on your subscription, you're signed in automatically, or you must provide your sign-in details for [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Viewing and Editing in Excel From Business Central](across-work-with-excel.md).  

The add-in lets you get fresh data from [!INCLUDE [prod_short](includes/prod_short.md)], and you can push changes back to [!INCLUDE [prod_short](includes/prod_short.md)]. However, the ability to push data back to the database is not available for the financial reports you can view in Excel.  

## Alternative to obsolete reports

Explore other ways to analyze your finance data. Learn more in [Financial analytics overview](bi.md).

## Related information

[Financial analytics overview](bi.md)  
[Viewing and Editing in Excel From Business Central](across-work-with-excel.md)  
[Finance overview](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
