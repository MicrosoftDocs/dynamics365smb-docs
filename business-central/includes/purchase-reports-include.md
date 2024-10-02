---
author: brentholtorf
ms.topic: include
ms.date: 04/08/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

The following table describes some of the key reports in the purchase module. The reports help different roles within the purchasing department make informed decisions to optimize their operations. 

| To... | Use report (CTRL+click to open in Business Central) | Learn more | Id | 
|-------|------------| ------------|----|
| Analyze vendor impact in cash flow and prioritise vendor payments. | [Vendor - Top 10 List](https://businesscentral.dynamics.com?report=311) | [About Vendor - Top 10 List](#vendor---top-10-list-report-311) | 311 |
| Keep track of vendor performance and ensure that your company is getting the best value for its money. | [Purchase statistics](https://businesscentral.dynamics.com?report=312) | [About Purchase statistics](#purchase-statistics-report-312) | 312 |
| Analyse your item purchases per vendor to manage inventory procurement and improve supply chain processes. Assess the relationship between discounts, cost amount, and volume of item purchases. | [Vendor/Item Purchases](https://businesscentral.dynamics.com?report=313) | [About Vendor/Item Purchases](#vendoritem-purchases-report-313) | 313 |


## Vendor - Top 10 List (report 311)

Try the report here: [Vendor - Top 10 List](https://businesscentral.dynamics.com?report=311)

### What the report does
The report provides a list of vendors with the most transactions within a selected period. You can choose to display more than 10 vendors.

The vendors are sorted by purchase amount within the selected period. The list gives a quick overview of vendors with the largest balance and highest purchase volume.


### Use cases
Use the report to ensure that vendor relationships are efficient and effective:
- Identify vendors with the most significant transaction volumes.
- Focus on strategic planning for major vendor negotiations.
- Monitor vendor performance and adjust procurement strategies accordingly.

For maintaining healthy relationships with your suppliers, use the report to:
- Monitor transaction frequency to gauge the reliability and performance of key suppliers.
- Plan upcoming payments to maintain good relationships and avoid payment delays.
- Identify potential issues with suppliers who have frequent transactions but may be causing cash flow problems.

To help ensure an overall efficiency of your supply chain, use the report to:
- Track vendor performance and ensure consistency in supply.
- Coordinate with finance and procurement teams to prioritize payments for essential vendors.
- Plan and execute strategic initiatives to maintain an efficient procurement process.

Within your finance department, use the report to 
- Prioritize vendor payments based on transaction volume.
- Ensure smooth cash flow by planning payments for high-volume vendors.
- Identify and mitigate potential cash flow issues before they escalate.



## Purchase statistics (report 312)

Try the report here: [Purchase statistics](https://businesscentral.dynamics.com?report=312)

### What the report does
[!INCLUDE [reports-purchase-statistics](reports-purchase-statistics.md)]

### Use cases

Use the report to keep track of vendor performance and ensure that your company is getting the best value for its money:
- Analyze total purchases, payments, and finance charges from each vendor.
- Compare the efficiency of different vendors over five periods.
- Identify trends in payment discounts taken or lost to inform negotiation strategies.

In your budgeting and financial forecasting processes, you can use the report to:
- Review financial outlays and cost savings from payment discounts.
- Monitor finance charges to ensure they are within acceptable limits.
- Use historical purchase data to project future spending.

For your accounts payable (AP) processes, use the report to ensure timely payments and manage discounts:
- Track upcoming payments and avoid missed discounts.
- Monitor overdue payments and the resulting finance charges.



## Vendor/Item Purchases (report 313)

Try the report here: [Vendor/Item Purchases](https://businesscentral.dynamics.com?report=313)

### What the report does

The report shows a total of items purchased from vendors in the given date period, grouped by vendors.

Value entries for each vendor/item combination are summed up to calculate the total invoiced quantity, cost amount and discount amount.

Added costs such as item charges are also included in the calculated cost amount.


### Use cases

Help ensure that your inventory levels are optimal:
- Track item purchases from vendors to manage stock levels.
- Identify purchasing trends to anticipate future inventory needs.
- Analyze the impact of discounts on inventory costs and make informed purchasing decisions.

Understanding and control your costs:
- Evaluate the total cost of purchased items including any additional charges.
- Assess the effectiveness of discounts in reducing overall procurement costs.
- Identify cost-saving opportunities by analyzing the relationship between item purchases and discounts.

Ensure that your procurement process is efficient and cost-effective:
- Compare invoiced quantities and amounts across different vendors.
- Identify which vendors offer the best discounts and terms.
- Optimize procurement strategies based on historical purchasing data.

Oversee the entire supply chain to ensure smooth operations:
- Monitor vendor performance and reliability based on item delivery data.
- Plan for future purchases by analyzing past transaction volumes and discount effectiveness.
- Manage vendor relationships by evaluating the total value received from each supplier.


## The old way

| Report | Description | Id | 
|---------|---------|---------|
|[Purchase statistics](https://businesscentral.dynamics.com?report=312)|[!INCLUDE [reports-purchase-statistics](reports-purchase-statistics.md)]|312|
|[Vendor - Top 10 list](https://businesscentral.dynamics.com?report=311)|Shows information on purchases from vendors for a selected period. You can choose the number of vendors that are included in the report.<br>The vendors are sorted in order of amount, and you can choose whether they're sorted by purchase amount or balance. The report gives a quick overview of the vendors from which you purchase the most or to which you owe the most.|311|
|[Vendor Item catalog](https://businesscentral.dynamics.com?report=320)|Displays a list of the vendors for the selected items or items for selected vendors. For each combination of item and vendor, it shows direct unit cost, lead time calculation and the vendor's item number.<br>In the US, Canada, and Mexico, this report isn't available. Instead, use the **Item/Vendor Catalog** (10164) report.|320|
|[Item/vendor catalog](https://businesscentral.dynamics.com?report=720)|Displays a list of the vendors for the selected items or items for selected vendors. For each combination of item and vendor, it shows direct unit cost, lead time calculation and the vendor's item number.<br>In the US, Canada, and Mexico, this report isn't available. Instead, use the **Item/Vendor Catalog** (10164) report.|720|
|[Vendor/Item Purchases](https://businesscentral.dynamics.com?report=313)|Shows a list of item entries for each vendor in a selected period. The report contains information on invoiced quantity, amount, and possible discounts. It can be used, for example, to analyze a company's item purchases and to show whether there's a relationship between discounts and item purchases.|313|
|[Inventory Cost and price list](https://businesscentral.dynamics.com?report=716)|Displays a list of price information for the selected items or stockkeeping units: direct unit cost, last direct cost, unit price, profit percentage, and profit.|716|
|[Inventory Availability Plan](https://businesscentral.dynamics.com?report=707)|If you would like to have an overview about specific items/stockkeeping units and their availability. This report will show you cumulated values such as gross requirements, scheduled and planned receipts, the inventory, and so on. |707|
|[Inventory Vendor Purchases](https://businesscentral.dynamics.com?report=714)|Displays a list of the vendors that your company has purchased items from within a selected period. It shows invoiced quantity, amount, and discount. The report can be used to analyze a company's item purchases.|714|
|[Inventory Purchase Orders](https://businesscentral.dynamics.com?report=709)|Displays a list of items on order from vendors. It also shows the expected receipt date and the quantity and amount on back orders. For example, use the report to see when items should be received, and whether a reminder of a back order should be issued|709|
|[Purchase Reservation Availability](https://businesscentral.dynamics.com?report=409)|Shows the availability of items for shipment on purchase documents, for example return orders. You determine whether the report indicates the status of each document or of each purchase line. <br>When you print the report, you can also update the quantity that is available for shipment in the **Qty. to Receive** field on the purchase lines. On purchase credit memos and negative purchase order lines, the **Qty. to Receive** field contains the quantity to ship.. Then you can use the report to determine which documents to ship. **Note**: This report isn't available for advanced warehouse functionality.|409|

<!--|[](https://businesscentral.dynamics.com?report=)Vendor detailed aging|11006| DACH specific: A report which could be used by the team leader of your purchased department as will the accounting. Here you will have an overview about the unpaid vendor invoices including the due dates, currencies and amounts. Basis is the open vendor ledger entries.| -->

