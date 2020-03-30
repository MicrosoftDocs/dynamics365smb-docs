---
title: Design Details - Cost Adjustment | Microsoft Docs
description: The main purpose of cost adjustment is to forward cost changes from cost sources to cost recipients, according to an item’s costing method, to provide correct inventory valuation.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Design Details: Cost Adjustment
The main purpose of cost adjustment is to forward cost changes from cost sources to cost recipients, according to an item’s costing method, to provide correct inventory valuation.  

An item can be sales invoiced before it has been purchase invoiced, so that the recorded inventory value of the sale does not match the actual purchase cost. Cost adjustment updates the cost of goods sold (COGS) for historic sales entries to ensure that they match the costs of the inbound transactions to which they are applied. For more information, see [Design Details: Item Application](design-details-item-application.md).  

The following are secondary purposes, or functions, of cost adjustment:  

* Invoice finished production orders:  

    * Change the status of value entries from **Expected** to **Actual**.  
    * Clear WIP accounts. For more information, see [Design Details: Production Order Posting](design-details-production-order-posting.md).  
    * Post variance. For more information, see [Design Details: Variance](design-details-variance.md).  

* Update the unit cost on the item card.  

Inventory costs must be adjusted before the related value entries can be reconciled with the general ledger. For more information, see [Design Details: Reconciliation with the General Ledger](design-details-reconciliation-with-the-general-ledger.md).  

## Detecting the Adjustment  
The task of detecting if cost adjustment should occur is primarily performed by the Item Jnl.-Post Line routine, while the task of calculating and generating cost adjustment entries is performed by the **Adjust Cost – Item Entries** batch job.  

To be able to forward costs, the detection mechanism determines which sources have changed in costs and to which destination these costs should be forwarded. The following three detection functions exist in [!INCLUDE[d365fin](includes/d365fin_md.md)]:  

* Item Application Entry  
* Average Cost Adjustment Entry Point  
* Order Level  

### Item Application Entry  
This detection function is used for items that use FIFO, LIFO, Standard, and Specific costing methods and for fixed applications scenarios. The function works as follows:  

* Cost adjustment is detected by marking the source item ledger entries as *Applied Entry to Adjust* whenever an item ledger entry or value entry is posted.  
* Cost is forwarded according to the cost chains that are recorded in the **Item Application Entry** table.  

### Average Cost Adjustment Entry Point  
This detection function is used for items that use the Average costing method. The function works as follows:  

* Cost adjustment is detected by marking a record in the **Avg. Cost Adjmt. Entry Point** table whenever a value entry is posted.  
* Cost is forwarded by applying the costs to value entries with a later valuation date.  

### Order Level  
This detection function is used in conversion scenarios, production and assembly. The function works as follows:  

* Cost adjustment is detected by marking the order whenever a material/resource is posted as consumed/used.  
* Cost is forwarding by applying the costs from material/resource to the output entries associated with the same order.  

The Order Level function is used to detect adjustments in assembly posting. The following graphic shows the adjustment entry structure:  

![Flow of entries in cost adjustment](media/design_details_assembly_posting_3.png "Flow of entries in cost adjustment")  

For more information, see [Design Details: Assembly Order Posting](design-details-assembly-order-posting.md).  

## Manual versus Automatic Cost Adjustment  
Cost adjustment can be performed in two ways:  

* Manually, by running the **Adjust Cost - Item Entries** batch job. You can run this batch job either for all items or for only certain items or item categories. This batch job runs a cost adjustment for the items in inventory for which an inbound transaction has been made, such as a purchase. For items that use the average costing method, the batch job also makes an adjustment if any outbound transactions are created.  
* Automatically, by adjusting costs every time that you post an inventory transaction, and when you finish a production order. The cost adjustment is only run for the specific item or items affected by the posting. This is set up when you select the **Automatic Cost Adjustment** check box on the **Inventory Setup** page.  

It is good practice to run the cost adjustment automatically when you post because unit costs are more frequently updated and therefore more accurate. The disadvantage is that the performance of the database can be affected by running the cost adjustment so often.  

Because it is important to keep the unit cost of an item up to date, it is recommend that you run the **Adjust Cost - Item Entries** batch job as often as possible, during nonworking hours. Alternatively, use automatic cost adjustment. This ensures that the unit cost is updated for items daily.  

Regardless if you run the cost adjustment manually or automatically, the adjustment process and its consequences are the same. [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the value of the inbound transaction and forwards that cost to any outbound transactions, such as sales or consumptions, which have been applied to the inbound transaction. The cost adjustment creates value entries that contain adjustment amounts and amounts that compensate for rounding.  

The new adjustment and rounding value entries have the posting date of the related invoice. Exceptions are if the value entries fall in a closed accounting period or inventory period or if the posting date is earlier than the date in the **Allow Posting From** field on the **General Ledger Setup** page. If this occurs, the batch job assigns the posting date as the first date of the next open period.  

## Adjust Cost - Item Entries Batch Job  
When you run the **Adjust Cost - Item Entries** batch job, you have the option to run the batch job for all items or for only certain items or categories.  

> [!NOTE]  
>  We recommend that you always run the batch job for all items and only use the filtering option to reduce the runtime of the batch job, or to fix the cost of a certain item.  

### Example  
The following example shows if you post a purchased item as received and invoiced on 01-01-20. You later post the sold item as shipped and invoiced on 01-15-20. Then, you run the **Adjust Cost - Item Entries** and **Post Inventory Cost to G/L** batch jobs. The following entries are created.  

**Value Entries**  

|Posting Date|Item Ledger Entry Type|Cost Amount (Actual)|Cost Posted to G/L|Invoiced Quantity|Entry No.|  
|------------------|----------------------------|----------------------------|-------------------------|-----------------------|---------------|  
|01-01-20|Purchase|10.00|10.00|1|1|  
|01-15-20|Sale|-10.00|-10.00|-1|2|  

**Relation Entries in the G/L – Item Ledger Relation Table**  

|G/L Entry No.|Value Entry No.|G/L Register No.|  
|--------------------|---------------------|-----------------------|  
|1|1|1|  
|2|1|1|  
|3|2|1|  
|4|2|1|  

**General Ledger Entries**  

|Posting Date|G/L Account|Account No. (En-US Demo)|Amount|Entry No.|  
|------------------|------------------|---------------------------------|------------|---------------|  
|01-01-20|[Inventory Account]|2130|10.00|1|  
|01-01-20|[Direct Cost Applied Account]|7291|-10.00|2|  
|01-15-20|[Inventory Account]|2130|-10.00|3|  
|01-15-20|[COGS Account]|7290|10.00|4|  

Later, you post a related purchase item charge for 2.00 LCY invoiced on 02-10-20. You run the **Adjust Cost - Item Entries** batch job and then run the **Post Inventory Cost to G/L** batch job. The cost adjustment batch job adjusts the cost of the sale by -2.00 LCY accordingly, and the **Post Inventory Cost to G/L** batch job posts the new value entries to the general ledger. The result is as follows.  

**Value Entries**  

|Posting Date|Item Ledger Entry Type|Cost Amount (Actual)|Cost Posted to G/L|Invoiced Quantity|Adjustment|Entry No.|  
|------------------|----------------------------|----------------------------|-------------------------|-----------------------|----------------|---------------|  
|02-10-20|Purchase|2.00|2.00|0|No|3|  
|01-15-20|Sale|-2.00|-2.00|0|Yes|4|  

**Relation Entries in the G/L – Item Ledger Relation Table**  

|G/L Entry No.|Value Entry No.|G/L Register No.|  
|--------------------|---------------------|-----------------------|  
|5|3|2|  
|6|3|2|  
|7|4|2|  
|8|4|2|  

**General Ledger Entries**  

|Posting Date|G/L Account|Account No. (En-US Demo)||Amount|Entry No.|  
|------------------|------------------|---------------------------------|-|------------|---------------|  
|02-10-20|[Inventory Account]|2130||2.00|5|  
|02-10-20|[Direct Cost Applied Account]|7291||-2.00|6|  
|01-15-20|[Inventory Account]|2130||-2.00|7|  
|01-15-20|[COGS Account]|7290||2.00|8|  

## Automatic Cost Adjustment  
To set up cost adjustment to run automatically when you post an inventory transaction, use the **Automatic Cost Adjustment** field on the **Inventory Setup** page. This field enables you to select how far back in time from the current work date that you want automatic cost adjustment to be performed. The following options exist.  

|Option|Description|  
|----------------------------------|---------------------------------------|  
|Never|Costs are not adjusted when you post.|  
|Day|Costs are adjusted if posting occurs within one day from the work date.|  
|Week|Costs are adjusted if posting occurs within one week from the work date.|  
|Month|Costs are adjusted if posting occurs within one month from the work date.|  
|Quarter|Costs are adjusted if posting occurs within one quarter from the work date.|  
|Year|Costs are adjusted if posting occurs within one year from the work date.|  
|Always|Costs are always adjusted when you post, regardless of the posting date.|  

The selection that you make in the **Automatic Cost Adjustment** field is important for performance and the accuracy of your costs. Shorter time periods, such as **Day** or **Week**, affect system performance less, because they provide the stricter requirement that only costs posted in the last day or week can be automatically adjusted. This means that the automatic cost adjustment does not run as frequently and therefore affects system performance less. However, it also means that unit costs may be less accurate.  

### Example  
The following example shows an automatic cost adjustment scenario:  

* On January 10, you post a purchased item as received and invoiced.  
* On January 15, you post a sales order for the item as shipped and invoiced.
* On February 5, you receive an invoice for a freight charge on the original purchase. You post this freight charge, applying it to the original purchase invoice, which increases the cost of the original purchase.  

If you have set up the automatic cost adjustment to apply to postings that occur within a month or a quarter from the current work date, then the automatic cost adjustment runs and forwards the cost of the purchase to the sale.  

If you have set up the automatic cost adjustment to apply to postings that occur within a day or a week from the current work date, then the automatic cost adjustment does not run, and the cost of the purchase is not forwarded to the sale until you run the **Adjust Cost - Item Entries** batch job.  

## See Also
[Adjust Item Costs](inventory-how-adjust-item-costs.md)   
[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Reconciliation with the General Ledger](design-details-reconciliation-with-the-general-ledger.md)   
[Design Details: Inventory Posting](design-details-inventory-posting.md)   
[Design Details: Variance](design-details-variance.md)   
[Design Details: Assembly Order Posting](design-details-assembly-order-posting.md)   
[Design Details: Production Order Posting](design-details-production-order-posting.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
