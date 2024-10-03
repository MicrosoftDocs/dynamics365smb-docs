---
author: brentholtorf
ms.topic: include
ms.date: 04/08/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

The following table describes some of the key reports in the purchase module. The reports help different roles within the purchasing department make informed decisions to optimize their operations. 

| To... | Open in Business Central (CTRL+click) | Learn more | Id | 
|-------|------------| ------------|----|
| Analyze vendor impact in cash flow and prioritise vendor payments. | [Vendor - Top 10 List](https://businesscentral.dynamics.com?report=311) | [About Vendor - Top 10 List](../reports/report-311.md) | 311 |
| Keep track of vendor performance and ensure that your company is getting the best value for its money. | [Purchase statistics](https://businesscentral.dynamics.com?report=312) | [About Purchase statistics](../reports/report-312.md) | 312 |
| Analyse your item purchases per vendor to manage inventory procurement and improve supply chain processes. Assess the relationship between discounts, cost amount, and volume of item purchases. | [Vendor/Item Purchases](https://businesscentral.dynamics.com?report=313) | [About Vendor/Item Purchases](#vendoritem-purchases-report-313) | 313 |




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

