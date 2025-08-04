---
title: Design details - average cost
description: The average cost of an item is calculated with a periodic weighted average.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords:
ms.search.form: 8645,
ms.date: 04/26/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Design details: average cost

The average cost of an item is calculated with a periodic weighted average. The average is based on the average cost period you have specified in [!INCLUDE[prod_short](includes/prod_short.md)].  

The valuation date is set automatically.  

## Setting up average cost calculation

The following table describes the two fields on the **Inventory Setup** page that must be filled to enable average cost calculation.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Average Cost Period**|Specifies which period the average cost is calculated in. The following options exist:<br /><br /> - **Day**<br />- **Week**<br />- **Month**<br />- **Accounting Period**<br /><br /> Inventory decreases that are posted in the average cost period get the average cost calculated for that period.|  
|**Average Cost Calc. Type**|Specifies how the average cost is calculated. The following options exist:<br /><br /> - **Item**<br />- **Item, Variant, and Location**<br /> With this option, the average cost is calculated for each item, for each location, and for each variant of the item. The average cost of this item depends on where you store it and the variant you select, such as color.|  

> [!NOTE]  
> You can only use one average cost period and one average cost calculation type in a fiscal year.  
>
> The **Accounting Periods** page shows which average cost period and which average cost calculation type is in effect during that period, for each accounting period.  

## Calculating average cost

 When you post a transaction for an item that uses the Average costing method, an entry is created in the **Avg. Cost Adjmt. Entry Point** table. This entry contains the transaction’s item number, variant code, and location code. The entry also contains the **Valuation Date** field, which specifies the last date of the average cost period in which the transaction was posted.  

> [!NOTE]  
> This field should not be confused with the **Valuation Date** field in the **Value Entry** table, which shows the date when the value takes effect and is used to determine the average cost period in which the value entry belongs.  

 The average cost of a transaction is calculated when the item’s cost is adjusted. For more information, see [Design Details: Cost Adjustment](design-details-cost-adjustment.md). A cost adjustment uses the entries in the **Avg. Cost Adjmt. Entry Point** table to identify which items (or items, locations, and variants) to calculate average costs for. For each entry with a cost that hasn't been adjusted, the cost adjustment uses the following to determine the average cost:  

- Determines the cost of the item at the start of the average cost period.  
- Adds the sum of the inbound costs that were posted during the average cost period. These include purchases, sales returns, positive adjustments, and production and assembly outputs.  
- Subtracts the sum of the costs of any outbound transactions that were fixed-applied to receipts in the average cost period. These typically include purchase returns and negative outputs.  
- Divides by the total inventory quantity for the end of the average cost period. Excludes inventory decreases that are being valued.  

 The calculated average cost is then applied to the inventory decreases for the item (or item, location, and variant) with posting dates in the average cost period. For inventory increases that are fixed-applied to inventory decreases in the average cost period, [!INCLUDE [prod_short](includes/prod_short.md)] forwards the calculated average cost from the increase to the decrease.  

### Example: average cost period = day

The following example shows the effect of calculating average cost based on an average cost period of one day. The **Average Cost Calc. Type** field on the **Inventory Setup** page is set to **Item**.  

The following table shows item ledger entries for the sample average-cost item, ITEM1, before you run the **Adjust Cost - Item Entries** batch job.  

| **Posting Date** | **Item Ledger Entry Type** | **Quantity** | **Cost Amount (Actual)** | **Entry No.** |
|--|--|--|--|--|
| 01-01-23 |   Purchase | 1 | 20.00 | 1 |
| 01-01-23 |   Purchase | 1 | 40.00 | 2 |
| 01-01-23 |   Sale | -1 | -20.00 | 3 |
| 02-01-23 |   Sale | -1 | -40.00 | 4 |
| 02-02-23 |   Purchase | 1 | 100.00 | 5 |
| 02-03-23 |   Sale | -1 | -100.00 | 6 |

> [!NOTE]  
> Because cost adjustment has not yet occurred, the values in the **Cost Amount (Actual)** field of the inventory decreases corresponding to the inventory increases that they are applied to.  

 The following table shows the entries in the **Avg. Cost Adjmt. Entry Point** table that apply to the value entries that result from the item ledger entries in the preceding table.  

| **Item No.** | **Variant Code** | **Location Code** | **Valuation Date** | **Cost is Adjusted** |
|--|--|--|--|--|
| ITEM1 |  | BLUE | 01-01-23 |   No |
| ITEM1 |  | BLUE | 02-01-23 |   No |
| ITEM1 |  | BLUE | 02-02-23 |   No |
| ITEM1 |  | BLUE | 02-03-23 |   No |

 The following table shows the same item ledger entries after you run the **Adjust Cost - Item Entries** batch job. The average cost per day is calculated and applied to the inventory decreases.  

| **Posting Date** | **Item Ledger Entry Type** | **Quantity** | **Cost Amount (Actual)** | **Entry No.** |
|--|--|--|--|--|--|
| 01-01-23 |   Purchase | 1 | 20.00 | 1 |
| 01-01-23 |   Purchase | 1 | 40.00 | 2 |
| 01-01-23 |   Sale | -1 | -30.00 | 3 |
| 02-01-23 |   Sale | -1 | -30.00 | 4 |
| 02-02-23 |   Purchase | 1 | 100.00 | 5 |
| 02-03-23 |   Sale | -1 | -100.00 | 6 |

### Example: average cost period = month

 This example shows the effect of calculating the average cost based on an average cost period of one month. The **Average Cost Calc. Type** field on the **Inventory Setup** page  is set to **Item**.  

 If the average cost period is one month, [!INCLUDE [prod_short](includes/prod_short.md)] creates one entry for each combination of item number, variant code, location code, and valuation date.  

 The following table shows item ledger entries for the sample average-cost item, ITEM1, before you run the **Adjust Cost - Item Entries** batch job.  

| **Posting Date** | **Item Ledger Entry Type** | **Quantity** | **Cost Amount (Actual)** | **Entry No.** |
|--|--|--|--|--|
| 01-01-23 |   Purchase | 1 | 20.00 | 1 |
| 01-01-23 |   Purchase | 1 | 40.00 | 2 |
| 01-01-23 |   Sale | -1 | -20.00 | 3 |
| 02-01-23 |   Sale | -1 | -40.00 | 4 |
| 02-02-23 |   Purchase | 1 | 100.00 | 5 |
| 02-03-23 |   Sale | -1 | -100.00 | 6 |

> [!NOTE]  
> Because cost adjustment has not occurred yet, the values in the **Cost Amount (Actual)** field of the inventory decreases corresponding to the inventory increases that they are applied to.  

The following table shows the entries in the **Avg. Cost Adjmt. Entry Point** table that apply to the value entries that result from the item ledger entries in the preceding table.  

| **Item No.** | **Variant Code** | **Location Code** | **Valuation Date** | **Cost is Adjusted** |
|--|--|--|--|--|
| ITEM1 |  | BLUE | 01-31-23 |   No |
| ITEM1 |  | BLUE | 02-28-23 |   No |

> [!NOTE]  
> The valuation date is set to the last day in the average cost period, which in this case is the last day of the month.  

The following table shows the same item ledger entries after you run the **Adjust Cost - Item Entries** batch job. The average cost per month is calculated and applied to the inventory decreases.  

|**Posting Date** | **Item Ledger Entry Type** | **Quantity** | **Cost Amount (Actual)** | **Entry No.** |
|--|--|--|--|--|
| 01-01-23 | Purchase | 1 | 20.00 | 1 |
| 01-01-23 | Purchase | 1 | 40.00 | 2 |
| 01-01-23 | Sale | -1 | -30.00 | 3 |
| 02-01-23 | Sale | -1 | -65.00 | 4 |
| 02-02-23 | Purchase | 1 | 100.00 | 5 |
| 02-03-23 | Sale | -1 | -65.00 | 6 |

The average cost of entry number 3 is calculated in the average cost period for January. The average cost for entries 4 and 6 is calculated in the average cost period for February.  

To get the average cost for February, [!INCLUDE [prod_short](includes/prod_short.md)] adds the average cost of the item received in inventory (100.00) to the average cost at the beginning of the period (30.00). The sum (130.00) is then divided by the total quantity in inventory (2). This calculation gives the resulting average cost of the item in the February period (65.00). The average cost is assigned to the inventory decreases in the period (entries 4 and 6).  

## Setting the valuation date

 The **Valuation Date** field in the **Value Entry** table determines the average cost period in which an inventory decrease entry belongs. This setting also applies to work in process (WIP) inventory.  

 The following table shows the criteria that are used to set the valuation date.  

| Scenario | Posting Date | Valued Quantity | Revaluation | Valuation Date |
|--|--|--|--|--|
| 1 |  | Positive | No | Posting date of item ledger entry |
| 2 | Later than the latest valuation date of applied value entries | Negative | No | Posting date of item ledger entry |
| 3 | Earlier than the latest valuation date of applied value entries | Positive | No | Latest valuation date of the applied value entries |
| 4 |  | Negative | Yes | Posting date of the revaluation value entry |

### Example

The following table of value entries illustrates the different scenarios.  

| Scenario | Posting Date | Item Ledger Entry Type | Valuation Date | Valued Quantity | Cost Amount (Actual) | Item Ledger Entry No. | Entry No. |
|--|--|--|--|--|--|--|--|
| 1 | 01-01-20 | Purchase | 01-01-20 | 2 | 20.00 | 1 | 1 |
| 2 | 01-15-20 | (Item Charge) | 01-01-20 | 2 | 8.00 | 1 | 2 |
| 3 | 02-01-20 | Sale | 02-01-20 | -1 | -14.00 | 2 | 3 |
| 4 | 03-01-20 | (Revaluation) | 03-01-20 | 1 | -.4.00 | 1 | 4 |
| 5 | 02-01-20 | Sale | 03-01-20 | -1 | -10.00 | 3 | 5 |

> [!NOTE]  
> In entry number 5 in the preceding table, the user has entered a sales order with a posting date (02-01-20) that comes before the latest valuation date of applied value entries (03-01-20). If the corresponding value in the **Cost Amount (Actual)** field for this date (02-01-20) were used for this entry, then it would be 14.00. This would give a situation where the quantity on inventory is zero, but the inventory value is –4.00.  
>
> To avoid such a quantity-value mismatch, the valuation date is set to equal the latest valuation date of the applied value entries (03-01-20). The value in the **Cost Amount (Actual)** field becomes 10.00 (after revaluation), which means that the quantity on inventory is zero, and the inventory value is also zero.  

> [!CAUTION]  
> Because the **Inventory Valuation** report is based on posting date, the report will reflect any quantity-value mismatches in scenarios as in the above example. For more information, see [Design Details: Inventory Valuation](design-details-inventory-valuation.md).  

If the quantity on inventory is less than zero after you post the inventory decrease, the valuation date is set to the posting date of the inventory decrease. You can change this date when the inventory increase is applied, according to the rules described in the note earlier in this section.  

## Recalculating average cost

Valuing inventory decreases as a weighted average would be straightforward in several scenarios:

- Purchases are always invoiced before sales.
- Postings are never backdated.
- You never made mistakes.

However, the reality is different.  

As the examples in this article illustrate, the valuation date is defined as the date from which the value entry is included in the average cost calculation. This setting lets you do several things for items with the Average costing method:  

- Invoice the sale of an item before you invoice its purchase.  
- Backdate a posting.  
- Recover an incorrect posting.  

> [!NOTE]  
> Another reason for this flexibility is fixed application. For more information about fixed application, see [Design Details: Item Application](design-details-item-application.md).  

Because of this flexibility, you might have to recalculate the average cost after posting. For example, if you post an inventory increase or decrease with a valuation date that's before an inventory decrease. The recalculation of the average cost occurs automatically when you run the **Adjust Cost - Item Entries** batch job, manually or automatically.  

You can change the inventory valuation base within an accounting period by changing the values in the **Average Cost Period** and **Average Cost Calc. Type** fields. However, we recommend that you use caution and consult your auditor.  

### Example of recalculated average cost

This example shows how [!INCLUDE [prod_short](includes/prod_short.md)] recalculates the average cost when you post on a date that's before an inventory decrease. The example is based on an average cost period of **Day**.  

The following table shows the value entries that exist for the item before the posting is introduced.  

| Valuation Date | Quantity | Cost Amount (Actual) | Entry No. |
|--|--|--|--|
| 01-01-20 | 1 | 10.00 | 1 |
| 01-02-20 | 1 | 20.00 | 2 |
| 02-15-20 | -1 | -15.00 | 3 |
| 02-16-20 | -1 | -15.00 | 4 |

The user posts an inventory increase (entry number 5) with a valuation date (01-03-20) that's before an inventory decrease. To balance the inventory, the average cost must be recalculated and adjusted to 17.00.  

The following table shows the value entries that exist for the item after entry number 5 is introduced.  

| Valuation Date | Quantity | Cost Amount (Actual) | Entry No. |
|--|--|--|--|
| 01-01-20 | 1 | 10.00 | 1 |
| 01-02-20 | 1 | 20.00 | 2 |
| 01-03-20 | 1 | 21.00 | 5 |
| 02-15-20 | -1 | -17.00 | 3 |
| 02-16-20 | -1 | -17.00 | 4 |

## Related information

[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Costing Methods](design-details-costing-methods.md)  
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)  
[Design Details: Item Application](design-details-item-application.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Glossary of terms in Dynamics 365 business processes](/dynamics365/guidance/business-processes/glossary)  
[Business process for product costing and how it relates to other processes with Dynamics 365](/dynamics365/guidance/business-processes/design-to-retire-define-product-costing-overview)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
