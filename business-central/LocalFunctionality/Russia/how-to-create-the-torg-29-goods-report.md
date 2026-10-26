---
title: Creating the TORG-29 goods report in Russia
description: Russian localization provides support for generating the TORG-29 goods report.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: TORG-29, TORG29, goods report, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Create TORG-29 Goods report

The TORG-29 report shows the item documents that you can use to submit for receipts and shipments for a location.  

When you run the report for a location, the **Last Goods Report No.** and **Last Goods Report Date** fields in the **Location Card** window are updated to ensure consistent reporting.

## Create the TORG-29 report

Configure **TORG-29 Template Code** in **Inventory Setup** before you run the report. A location, responsible employee, report acceptor, and valid start and end dates are required.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Report TORG-29**, and then choose the related link.

1. On the **Options** FastTab, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **Location Code** | Specifies the location that the report is for. |
   | **Report No.** | Specifies the number of times that the report has printed based on the value of the **Last Goods Report No.** field in the **Location Card** window. |
   | **Responsible Employee** | Specifies the employee who is responsible for the validity of the data in the report. |
   | **Report Acceptor** | Specifies the employee who is responsible for accepting the report. |
   | **Report Date** | Specifies the date of the report. |
   | **Start Date** | Specifies the start date for the report. |
   | **End Date** | Specifies the end date for the report. |
   | **Operation Type** | Optionally, specifies the type of operation. This information is included in the report. |
   | **Attaches No.** | Specifies the number of attachments to the report. |
   | **Receipt Detailing** | Specifies what the detailed information for each entry is based on.   If you select **Document**, amounts are totaled for each document. If you select **Item**, the amount and quantity are totaled for each item. If you select **Operation**, the amount and quantity are included in a single transaction. |
   | **Shipment Detailing** | Specifies what the detailed information for each entry is based on.   If you select **Total Amount**, the report summarizes amounts in a single line. If you select **Document**, amounts are totaled for each document. If you select **Item**, the amount and quantity are totaled for each item. If you select **Operation**, the amount and quantity are included in a single transaction. |
   | **Amount Type** | Specifies what the amounts are based on, cost or sales price. If you set this field to **Sales Price**, the **Sales Type**, **Show Cost Amount for Receipts**, and **Show Cost Amount for Shipment** fields become available. |
   | **Sales Type** | Specifies the source of sales prices: **Customer Price Group**, **All Customers**, or **Campaign**. For a customer price group or campaign, select the corresponding code in **Sales Code**. |
   | **Sales Code** | Specifies the price list. Depending on the selection in the **Sales Type** field, you can specify either a customer price group or a campaign number. |
   | **Show Cost Amount for Receipts** | Specifies if each receipt line must be divided into two lines. If selected, the first line for a receipt represents item cost, and the second line represents the sales margin. |
   | **Show Cost Amount for Shipment** | Specifies whether each shipment line is divided into two lines. If selected, the first line represents the item cost, and the second line represents the sales margin. |

1. Choose **OK** to export the report to Excel. Print the exported workbook from Excel.

## Related information

[Setting Up Inventory](../../inventory-setup-inventory.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
