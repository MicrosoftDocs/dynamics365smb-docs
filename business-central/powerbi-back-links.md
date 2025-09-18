---
title: Use back links to explore aggregated data in visuals  
description: When you're analyzing a visual in Power BI, back links let you go to the data behind the graphic.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.service: dynamics-365-business-central
ms.search.keywords: privacy, trial, Microsoft services
ms.date: 06/11/2025
ms.custom: bap-template
---

# Use back links to explore the data behind visuals

Back links make it easy to go from the aggregated data in reports in Power BI to the transactional data or source documents behind it in [!INCLUDE [prod_short](includes/prod_short.md)]. The connection between the visuals and the backstory lets you quickly validate, audit, and reconcile figures.

## Where you can expect to find back links

Back links are added to tables and matrices that display aggregated values or detail entries in Power BI. Some examples include:

- [**Daily Sales by Date**](sales-powerbi-daily-sales.md): Quickly go to detailed sales transactions for a specific day.
- [**Income Statement by Month**](finance-powerbi-income-statement.md): View the underlying G/L entries for monthly financial summaries.
- [**Moving Annual Total Details**](purchases-powerbi-moving-annual-total.md): Drill down to transaction-level details for moving annual totals.

## How back links work

Back links use custom Data Analysis Expressions (DAX) measures to dynamically generate web URLs that link to the [!INCLUDE [prod_short](includes/prod_short.md)] instance connected to the Power BI report.

The DAX measure retrieves and concatenates the **Tenant ID**, **Environment Name**, and **Company Name** from the report parameters and queries.

The filter context in Power BI, such as the **Date** filter, and other key fields construct the URL. The URL filters the relevant transactions or documents in [!INCLUDE [prod_short](includes/prod_short.md)] that correspond to the data displayed in the Power BI report.

## Example

This example uses the [**Income Statement by Month**](finance-powerbi-income-statement.md) matrix in the Power BI Finance App to illustrate the advantages that back links provide.

The **Income Statement by Month** matrix in Power BI shows aggregated financial figures by G/L accounts and months.

Without back links, you typically need to:

1. Drill through the numbers in Power BI.
2. Manually note the entry numbers.
3. Reconcile and locate the entries in [!INCLUDE [prod_short](includes/prod_short.md)].

However, with back links:

- Links are added to both Level 1 accounts and sublevel accounts in the matrix.
- Clicking a back link takes you to the detailed entries in [!INCLUDE [prod_short](includes/prod_short.md)] that make up the aggregated figure.
- If a **Date Filter** is applied in Power BI, the URL includes it to filter the transactions in [!INCLUDE [prod_short](includes/prod_short.md)].

For example, to show the transactions that make up the figure of the "5460 Cost of Capacities" account for January 2021, the URL displays the filtered G/L entries in [!INCLUDE [prod_short](includes/prod_short.md)].

:::image type="content" source="media/powerbi-back-links-income-statement-by-month.png" alt-text="Screenshot of the Income Statement by Month Power BI report with back links." lightbox="media/powerbi-back-links-income-statement-by-month.png":::

:::image type="content" source="media/powerbi-back-links-filtered-gl-entries.png" alt-text="Screenshot of the General Ledger Entries that make up the aggregated figure in Power BI" lightbox="media/powerbi-back-links-filtered-gl-entries.png":::

## Limitations

Currently, back links don't consider all visual and page filters applied in the Power BI report. The URL includes only **Date Filters**.

## Related information

[Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]](across-powerbi-install-business-central-apps.md)  
[Power BI apps/reports for functional areas](across-powerbi-apps-by-functional-area.md)  
[Frequently asked questions about the Power BI apps in Business Central](across-powerbi-apps-faq.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
