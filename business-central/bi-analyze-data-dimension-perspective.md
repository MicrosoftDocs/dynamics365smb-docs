---
title: Analyze data for some or all values of a dimension
description: Learn how to set up dimension perspectives that let you analyze data for all dimension values in one financial report.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/17/2026
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 8364_Primary,
---

# Analyze data for some or all values of a dimension

You can set up financial report dimension perspectives to analyze data for some or all of a dimension's values in one report. For example, if you want to analyze data for all of the departments that are dimension values for the Department dimension. After you create a perspective, you can use it in multiple reports.

## View report results

When you send a report to PDF, the dimension perspective creates a report for each dimension value and organizes them in rows. You might notice a mismatch between the number of pages that the PDF viewer lists and the number of pages that the report includes. The mismatch can happen because each page has multiple reports, but the PDF viewer thinks there's one page for each report.

Financial report dimension perspectives also work if you send your report results to Excel. The worksheet contains a tab for the main report, and tabs for each dimension value.

## Set up a financial report dimension perspective

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Financial Report Dimension Perspective**, and then choose the related link.
1. In the **Name** field, enter a name that indicates the use or subject of the perspective.
1. In the **Description** field, enter a brief description of the perspective.
1. Optionally, in the **Analysis View** field, specify the view that you want to apply to the results. Learn more at [Analyze data by dimensions](bi-how-analyze-data-dimension.md).
1. In the **Internal Description** field, provide more context about the perspective, for example, so someone else can quickly understand what it does. The final report doesn't show this description.
1. Choose the **Edit definition** action.
1. In the **Perspective Type** field, specify how you want to total values for the perspective.

   > [!TIP]
   > The **Custom** perspective type lets you set up more advanced totaling. For example, you can set up a perspective to total multiple dimension values from multiple dimensions. Learn more at [Set up custom totaling](#set-up-custom-totaling).

## Set up custom totaling

If you specify **Custom** as the perspective type for a perspective, you can set up your perspective to total amounts across dimensions to meet your specific needs.

In the **Perspective Header** field, indicate what the totaling includes, and then use the other fields to specify your combinations.

## Related information

[View a financial report on-screen, as a PDF, or in Excel](finance-financial-reporting-view-a-report.md)   
[Prepare financial reporting with financial data and account categories](bi-how-work-account-schedule.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]


