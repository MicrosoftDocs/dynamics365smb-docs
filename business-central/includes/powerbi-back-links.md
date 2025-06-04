# Back Links 
 
The Back Links functionality provides a seamless way to navigate between aggregated data in Power BI and the corresponding detailed transactional data or source documents in Dynamics 365 Business Central. This functionality enhances the user experience by allowing quick validation and auditing of figures directly in Business Central.

In tables and matrices, you can use back links to navigate directly to the related transactions in Business Central. This feature eliminates the need to manually reconcile numbers, making it easier to validate and audit data across systems.
 
## Where you can expect to see it
 
Back Links are added to tables and matrices that display aggregated values or detail entries in Power BI. Some examples include:
1. [**Daily Sales by Date**](../sales-powerbi-daily-sales.md): Quickly navigate to detailed sales transactions for a specific day.
2.	[**Income Statement by Month**](../finance-powerbi-income-statement.md): View the underlying G/L entries for monthly financial summaries.
3.	[**Moving Annual Total Details**](../purchases-powerbi-moving-annual-total.md): Drill down to transaction-level details for moving annual totals.

## How It Works
 
Back Links leverage custom DAX measures to dynamically generate web URLs that navigate to the relevant Business Central instance connected to the Power BI report.

The DAX measure retrieves and concatenates the **Tenant ID**, **Environment Name**, and **Company Name** from the report parameters and queries.

The generated URL points to the Business Central environment associated with the Power BI report.

The filter context in Power BI such as the Date filter and other key fields is used to dynamically construct the URL. This ensures that the URL filters the relevant transactions or documents in Business Central that correspond to the data displayed in the Power BI report.

 
## Example
Using the [**Income Statement by Month**](../finance-powerbi-income-statement.md) matrix in the Power BI Finance App.

The Income Statement by Month matrix in Power BI shows aggregated financial figures by G/L Accounts and Months. Without Back Links, users typically need to:
1.	Drill through the numbers in Power BI.
2.	Manually note down the entry numbers.
3.	Reconcile and locate these entries in Business Central.

With Back Links:
- Links are added to both Level 1 accounts and sub-level accounts in the matrix.
- Clicking a back link navigates directly to the detailed entries in Business Central that make up the aggregated figure.
- If a "Date Filter" is applied in Power BI, it is included in the URL to filter the transactions in Business Central accordingly.

For example, if you want to view the transactions that make up the figure of the "5460 Cost of Capacities" account for January 2021, the resulting URL will display the filtered General Ledger Entries in Business Central.

:::image type="content" source="media/powerbi-back-links-income-statement-by-month.png" alt-text="Screenshot of the Income Statement by Month Power BI report with back links" lightbox="media/powerbi-back-links-income-statement-by-month.png":::

:::image type="content" source="media/powerbi-back-links-filtered-gl-entries.png" alt-text="Screenshot of the General Ledger Entries that make up the aggregated figure in Power BI" lightbox="media/powerbi-back-links-filtered-gl-entries.png":::

## Limitations
 Currently, Back Links do not consider all visual and page filters applied in the Power BI report. Only Date Filters are included in the URL.
