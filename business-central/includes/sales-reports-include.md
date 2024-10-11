---
author: brentholtorf
ms.topic: include
ms.date: 01/29/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

The following table describes some of the key reports in or related to the sales module. The reports help different roles within the sales department make informed decisions to optimize their operations. 

| To... | Open in Business Central (CTRL+click) | Learn more | Id | 
|-------|------------| ------------|----|
| Analyse your nonshipped orders in order to understand your expected sales volume. Assists you to forecast your expected monthly sales revenue. | [Customer - Order Summary](https://businesscentral.dynamics.com?report=107) | [About *Customer - Order Summary*](../reports/report-107.md) | 107 |
| Analyse your outstanding sales orders to understand your expected sales volume grouped by customer. Compare your overall outstanding shipments with the planned shipment date to highlight any overdue back orders. | [Customer - Order Detail](https://businesscentral.dynamics.com?report=108) | [About *Customer - Order Detail*](../reports/report-108.md) | 108 |
| Review customers with the most transactions within a selected period to identify sales trends and manage collectable debts. | [Customer - Top 10 list](https://businesscentral.dynamics.com?report=111) | [About *Customer - Top 10 list*](../reports/report-111.md) | 111 |
| Analyze earnings from an individual customer or earnings trends. | [Sales Statistics](https://businesscentral.dynamics.com?report=112) <br><br>**Note!** In the US, Canada, and Mexico, this report is not available. Instead, use the **Customer Sales Statistics** ([10047](https://businesscentral.dynamics.com?report=10047)) report. | [About *Sales Statistics*](../reports/report-112.md) | 112 |
| Analyse your item sales per customer to understand sales trends, optimise inventory management and improve marketing efforts. Assess the relationship between discounts, sales amount and volume of item sales. | [Customer/Item Sales](https://businesscentral.dynamics.com?report=113) | [About *Customer/Item Sales*](../reports/report-113.md) | 113 |
| Get an overview of customer sales for a period. You can use it to report to the customs and tax authorities. | [Customer - Sales list](https://businesscentral.dynamics.com?report=119) | [About *Customer - Sales list*](../reports/report-119.md) | 119 |
| Generate customer statements, providing a clear summary of amounts due, which can be shared with customers for payment follow-ups, especially in connection to the close of an accounting period or fiscal year. | [Customer - Balance to date](https://businesscentral.dynamics.com?report=121) | [About *Customer - Balance to date*](../reports/report-121.md) | 121 |
| Analyse and reconcile your customer balances at the end of the period by seeing the opening balance, each transaction within the period and the closing balance grouped by customer. | [Customer - Trial Balance](https://businesscentral.dynamics.com?report=129) | [About *Customer - Trial Balance*](../reports/report-129.md) | 129 |
| Get an overview of which items are available to fulfill sales orders and help ensure that inventory reservations are accurate | [Sales Reservation Avail.](https://businesscentral.dynamics.com?report=209) | [About *Sales Reservation Avail.*](../reports/report-209.md) | 209 |
| Analyse your outstanding sales orders to understand your expected sales volume grouped by item. Compare your overall outstanding shipments with the planned shipment date to highlight any overdue back orders. | [Inventory Order Details](https://businesscentral.dynamics.com?report=708) | [About *Inventory Order Details*](../reports/report-708.md) | 708 |

|  | [Inventory Sales Back Orders](https://businesscentral.dynamics.com?report=718) | [About *Inventory Sales Back Orders*](../reports/report-718.md) | 718 |

|[Inventory Sales Back Orders](https://businesscentral.dynamics.com?report=718)|Shows a list with the order lines whose shipment date has been exceeded. The following information is shown for the individual orders for each item: number, customer name, customer's telephone number, shipment date, order quantity and quantity on back order. The report also shows whether there are other items for the customer on back order.|718|


<!-- 
|  | [](https://businesscentral.dynamics.com?report=) | [About **](../reports/report-.md) |  |

718
813
7313
-->

## The old way
The following table describes some of the key reports in sales reporting.

| Report | Description | Id | 
|---------|---------|---------|
|[Customer - Order Summary](https://businesscentral.dynamics.com?report=107)| Shows the order detail with the quantity not yet shipped for each customer in three periods of 30 days each, starting from the specified date. There are also columns with orders to be shipped before and after the three periods and a column with the total order detail for each customer. Use the report to analyze a company's expected sales volume. |107|
|[Customer - Top 10 list](https://businesscentral.dynamics.com?report=111)| Shows information on customers' purchases and balances for a selected period. You can choose the number of customers that will be included in the report. Only customers that have either purchases during the period or a balance at the end of the period will be included.<br>The customers are sorted in order of amount, and you can choose whether they're sorted by sales amount or balance. The report gives a quick overview of the customers that purchase the most or that owe the most.|111|
|[Customer/Item Sales](https://businesscentral.dynamics.com?report=113)|Shows a list of item sales for each customer during a selected time period. The report contains information on quantity, sales amount, profit, and possible discounts. It can be used, for example, to analyze a company's customer groups.|113|
|[Inventory - Customer Sale](https://businesscentral.dynamics.com?report=713)|An overview from the perspective of the warehouse sight. This is a different view compared to the **Customer/Item sale** report, and it shows the item first and then the customer who bought this product.|713|
|[Customer - Sales list](https://businesscentral.dynamics.com?report=119)|Shows customer sales for a period. You use it to report to the customs and tax authorities. You can choose to include only customers with total sales that exceed a minimum amount. You can also specify whether you want the report to show address details for each customer.<br>The report is based on recorded sales (LCY) from customer ledger entries. At the bottom of the report, the total reported sales are shown in LCY. The total is based on the customers you have included in the report, that is, the customers that are within the filters on the Customer FastTab and have total sales greater than the amount specified in the **Amounts (LCY) Greater Than** field on the **Options** FastTab.|119|
|[Customer - Balance to date](https://businesscentral.dynamics.com?report=121)|Shows a detailed balance for selected customers. Use the report at the close of an accounting period or fiscal year, for example.|121|
|[Customer - Trial Balance](https://businesscentral.dynamics.com?report=129)|Shows a detail balance for selected customers. You can use the report to verify that the balance for a customer posting group is equal to the balance on the corresponding G/L account on a certain date. Use the report at the close of an accounting period or fiscal year, for example. If you need a more detailed version of this type of report, use the **Customer Detail Trial Balance** (104) report.| 129 |
|[Sales Statistics](https://businesscentral.dynamics.com?report=112)|[!INCLUDE [reports-sales-statistics](reports-sales-statistics.md)] | 112|
|[Sales Reservation Avail.](https://businesscentral.dynamics.com?report=209)|Shows the availability of items for shipment on sales documents. You determine whether the report indicates the status of each document or of each sales line. When you print the report, you can also update the quantity that is available for shipment in the **Qty. to Ship** field on the sales lines. Then you can use the report to determine which documents to post.<br>There's also a capability with which you could set the amount of goods to be shipped. **Note**: This report isn't available for advanced warehouse functionality.| 209 |
|[Warehouse Shipment Status](https://businesscentral.dynamics.com?report=7313)|This report can be used for all locations where the **Require Shipment** field is selected. The **Warehouse Shipment Status** report shows you all unposted warehouse shipment documents, including the locations, bin codes, document status, quantities, and so on. This report is perfect to get an overview.| 7313 |
|[Inventory Picking List](https://businesscentral.dynamics.com?report=813)|Displays a list of the sales orders in which an item is included. The following information is shown for each item: Sales order line with the name of the customer, variant code, location code, bin code, shipment date, quantity to be shipped, and unit of measure. The quantity to be shipped is totaled for each item. The report can be used when items will be collected from the inventory.<br>**Note**: This report isn't available for advanced warehouse functionality.|813|
|[Inventory Sales Back Orders](https://businesscentral.dynamics.com?report=718)|Shows a list with the order lines whose shipment date has been exceeded. The following information is shown for the individual orders for each item: number, customer name, customer's telephone number, shipment date, order quantity and quantity on back order. The report also shows whether there are other items for the customer on back order.|718|
|[Inventory Order Details](https://businesscentral.dynamics.com?report=708)|Displays a list of the orders that haven't yet been shipped and the items in the orders. It shows the order number, customer's name, shipment date, order quantity, delayed quantity, outstanding quantity, and unit price, as well as any potential discount percentage and amount. The quantity on back order and outstanding quantity and amount are totaled for each item. Use the report to find out whether there are currently shipment problems or any can be expected.|708|