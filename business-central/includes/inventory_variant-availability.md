---
author: brentholtorf
ms.topic: include
ms.date: 09/21/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
When you open the **Item Availability by Variant** page from a document line, then you can insert a variant in the document line by selecting the line with the variant that you want to insert and then choosing the OK button. If you've only used the page to view availability and don't want to insert a variant, then close the page without choosing the OK button.

The page shows one line for each period. Each line shows the item’s availability figures in the following key fields:

| Field | Description |
|--|--|
| **Gross Requirement**| Specifies the sum of the total demand for the item. The gross requirement consists of *independent demand* and *dependent demand*. *Independent demand* includes sales orders, service orders, transfer orders, and production forecasts. *Dependent demand* includes production order components for planned, firm planned, and released production orders. It also includes requisition and planning worksheets lines.|
| **Scheduled Receipt** | Specifies the sum of items from replenishment orders. The calculation includes firm planned and released production orders, purchase orders, and transfer orders. |
| **Planned Order Receipt** | Specifies the sum of items from planned production orders. |
| **Projected Available Balance** | Specifies the calculated available inventory. |
| **Planned Order Releases** | Specifies the sum of items from replenishment order proposals. The calculation includes planned production orders. it also includes planning or requisition worksheets lines that are calculated according to the starting date in the planning worksheet and production order or the order date in the requisition worksheet. This sum isn't included in the projected available inventory. However, it indicates which quantities should be converted from planned to scheduled receipts. |
