---
title: Set Up General Inventory Information
description: Describes how to define the general inventory setup so that you can manage your warehouse and stock.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: warehouse, stock
ms.search.form: 30, 456, 461
ms.date: 07/28/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up General Inventory Information

You specify your general inventory setup on the **Inventory Setup** page.

## To set up general inventory information

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. On the **Inventory Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### To set up inventory valuation and costing

To make sure that inventory costs are recorded correctly, you must set up various fields and pages before you begin to make item transactions. Typically, businesses choose a specific costing method and apply that to inventory items, for example, to help them track the value of items on stock.  

|**Field**|**Details**|  
|------------|-------------|
|**Automatic Cost Posting**|Ensure that the cost is automatically posted to the general ledger whenever an inventory transaction is posted. The field is turned on by default to ensure that inventory values are always correct in the general ledger. Alternatively, you can manually post costs at regular intervals with the **Post Inventory Cost to G/L** batch job. You can also turn off automatic cost posting. A notification displays from which you can start an assisted setup guide to help you schedule tasks for the job queue.  For detailed information, see [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md)|
|**Automatic Cost Adjustment**| Specifies if item value entries are automatically adjusted when an item transaction is posted. The field is set to *Always* by default to ensure that inventory values are always correct, which in turn keeps your sales and profit statistics up to date. The cost adjustment forwards any cost changes from inbound entries, such as those for purchases or production output, to the related outbound entries, such as sales or transfers. This is helpful for new [!INCLUDE[prod_short](includes/prod_short.md)] customers and small businesses with relatively low inventory transaction levels. However, as a business grows and inventory levels increase, this can slow down system performance. To minimize reduced performance during posting, select a time option to define how far back in time from the work date an inbound transaction can occur to potentially trigger adjustment of related outbound value entries. Alternatively, you can manually adjust costs at regular intervals with the **Adjust Cost - Item Entries** batch job. You can also set the **Automatic Cost Adjustment** field to *Never*. A notification displays from which you can start an assisted setup guide to help you schedule tasks for the job queue. For detailed information, see [Adjust Item Costs](inventory-how-adjust-item-costs.md)|
|**Expected Cost Posting to G/L**|Ensure that expected costs are posted to the general ledger to see from the interim G/L accounts an estimate of the amounts due and the cost of the traded items before they are actually invoiced. For detailed information, see [Design Details: Expected Cost Posting](design-details-expected-cost-posting.md) and [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md).|
|**Average Cost Calc. Type**|Define if the average cost is to be calculated per item only or per item for each stockkeeping unit and for each variant of the item. For detailed information, see [Design details: average cost](design-details-average-cost.md).|
|**Average Cost Period**|Select the period of time you would like application to use for calculating the weighted average cost of items that use the average costing method.  For detailed information, see [Design details: average cost](design-details-average-cost.md).|
|**Default Costing Method**|Select the default costing method that determines whether an actual or a budgeted value is capitalized and used in the cost calculation. You can select a different costing method for a specific item either by selecting item template where costing method is defined or by manualy selecting a different value on the **Item Card** page. For detailed information, see [Design details: costing methods](design-details-costing-methods).|

For more information about costing in general, see [Managing Inventory Costs](finance-manage-inventory-costs.md).  


If you want to include warehouse handling time in the order promising calculation on the purchase line, you can set it up as a default for the inventory, on the **Inventory Setup** page, and for your location. For more information, see [Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md).  



## See Also

[Set Up Inventory](inventory-setup-inventory.md)  
[Manage Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
