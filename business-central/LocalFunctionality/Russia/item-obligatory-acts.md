---
title: Item obligatory acts in Russia
description: Russian localization provides support for item obligatory acts and related reporting.
author: DianaMalina
ms.topic: article
ms.search.keywords: Item obligatory acts, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Item obligatory acts

The item obligatory acts feature provides reports for your company's material and production resources. These reports contain item information such as the item number, description, storage place, brand, sort, profile, size, unit of measure, and vendor information. Confirm which forms your organization needs.

You can print reports for the various accounts used for material and production resources.

The following table provides the list of reports and how to print the reports.

Before you generate a report, configure its template in the corresponding setup page. For example, configure **Item Card M-17 Template Code** in **Inventory Setup** and **M-4 Template Code** in **Purchases & Payables Setup**. Sales shipment templates are configured in **Sales & Receivables Setup**. When **Print** opens **Report Selection - Print**, select the **Print Report** check box on the row for the required report, and choose **OK**. Fill in the report's request page, and choose **OK** to export an Excel workbook. Print the workbook from Excel.

| Report | Description |
|--|--|
| Item Card M-17 | Records item movements for a reporting period and includes fields for responsible employees' signatures. Run **Item Card M-17** for the required items and dates. |
| Physical Inventory Form INV-3 (inventory description) | Records physical inventory results. In **Phys. Inventory Journal**, choose **Print** and select the **Phys. Inventory Form INV-3** row if the report selection page opens. |
| Physical Inventory Form INV-19 (comparison sheet) | Compares inventory results. In **Phys. Inventory Journal**, choose **Print** and select the **Phys. Inventory Form INV-19** row if the report selection page opens. Enter the inventory basis, document number and date, inventory start and end dates, document creation date, and as-of date on the request page. |
| Transfer Order TORG-13 (internal transfer order) | Records an internal transfer of items and packaging. Open the transfer order, choose **Print**, and select the **Transfer Order TORG-13** row if the report selection page opens. |
| Shipment Request M-11 | Records an internal transfer of materials. In **Item Reclass. Journal**, choose **Print** and select the **Shipment Request M-11** row if the report selection page opens. Enter the entry type code, sender, and sending and receiving employees on the request page. |
| Warehouse Purchase Receipt M-4 | Records receipt of items and materials at the warehouse. Open a purchase order or posted purchase invoice, choose **Print**, and select the corresponding **Purchase Receipt M-4** report row if the report selection page opens. |
| Sales Shipment M-15 | Records shipment of materials out of the company. Open a sales order, sales invoice, or posted sales invoice. Release an unposted document before you generate the report. Choose **Print**, and select the corresponding **Sales Shipment M-15** report row if the report selection page opens. |

## Related information

- [Item Documents](item-documents.md)  
- [Item General Ledger Turnover](item-general-ledger-turnover.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
