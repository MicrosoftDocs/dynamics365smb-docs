# Back Links

Back links make it easy to go from the aggregated data in Power BI to the transactional data or source documents behind it in [!INCLUDE [prod_short](prod_short.md)]. The connection between the visuals and the backstory lets you quickly validate, audit, and reconcile figures.

## Where you can expect to find back links

Back links are added to tables and matrices that display aggregated values or detail entries in Power BI. Some examples include:

- [**Daily Sales by Date**](../sales-powerbi-daily-sales.md): Quickly go to detailed sales transactions for a specific day.
- [**Income Statement by Month**](../finance-powerbi-income-statement.md): View the underlying G/L entries for monthly financial summaries.
- [**Moving Annual Total Details**](../purchases-powerbi-moving-annual-total.md): Drill down to transaction-level details for moving annual totals.

## How back links work

Back links leverage custom Data Analysis Expressions (DAX) measures to dynamically generate web URLs that link to the [!INCLUDE [prod_short](prod_short.md)] instance connected to the Power BI report.

The DAX measure retrieves and concatenates the **Tenant ID**, **Environment Name**, and **Company Name** from the report parameters and queries.

The filter context in Power BI, such as the **Date** filter, and other key fields construct the URL. The URL filters the relevant transactions or documents in [!INCLUDE [prod_short](prod_short.md)] that correspond to the data displayed in the Power BI report.

## Example

This example uses the [**Income Statement by Month**](../finance-powerbi-income-statement.md) matrix in the Power BI Finance App to illustrate the advantages that back links provide.

The **Income Statement by Month** matrix in Power BI shows aggregated financial figures by G/L accounts and months.

Without back links, you typically need to:

1. Drill through the numbers in Power BI.
2. Manually note the entry numbers.
3. Reconcile and locate the entries in [!INCLUDE [prod_short](prod_short.md)].

However, with back links:

- Links are added to both Level 1 accounts and sub-level accounts in the matrix.
- Clicking a back link takes you to the detailed entries in [!INCLUDE [prod_short](prod_short.md)] that make up the aggregated figure.
- If a **Date Filter** is applied in Power BI, it's included in the URL to filter the transactions in [!INCLUDE [prod_short](prod_short.md)].

For example, if you want to review the transactions that make up the figure of the "5460 Cost of Capacities" account for January 2021, the resulting URL displays the filtered G/L entries in [!INCLUDE [prod_short](prod_short.md)].

:::image type="content" source="media/powerbi-back-links-income-statement-by-month.png" alt-text="Screenshot of the Income Statement by Month Power BI report with back links" lightbox="media/powerbi-back-links-income-statement-by-month.png":::

:::image type="content" source="media/powerbi-back-links-filtered-gl-entries.png" alt-text="Screenshot of the General Ledger Entries that make up the aggregated figure in Power BI" lightbox="media/powerbi-back-links-filtered-gl-entries.png":::

## Limitations

Currently, back links don't consider all visual and page filters applied in the Power BI report. The URL includes only **Date Filters**.
