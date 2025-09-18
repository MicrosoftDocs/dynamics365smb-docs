---
title: Set up general inventory information
description: Describes how to define the general inventory setup so that you can manage your warehouse and stock.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: warehouse, stock
ms.search.form: 30, 456, 461
ms.date: 02/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Set up general inventory information

You specify your general inventory setup on the **Inventory Setup** page.

## To set up general inventory information

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Inventory Setup**, and then choose the related link.
2. On the **Inventory Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### To set up inventory valuation and costing

To record inventory costs correctly, you must set up various fields and pages before you make transactions that include item. Typically, businesses choose a specific costing method and apply that to inventory items, for example, to help them track the value of items on stock.  

|**Field**|**Details**|  
|------------|-------------|
|**Automatic Cost Posting**|Ensure that the cost is automatically posted to the general ledger whenever an inventory transaction is posted. The field is turned on by default to ensure that inventory values are always correct in the general ledger. Alternatively, you can manually post costs at regular intervals with the **Post Inventory Cost to G/L** batch job. You can also turn off automatic cost posting. A notification displays from which you can start an assisted setup guide to help you schedule tasks for the job queue. To learn more, go to [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md).|
|**Automatic Cost Adjustment**| Specifies if item value entries are automatically adjusted when an item transaction is posted. The field is set to **Always** by default to ensure that inventory values are always correct, which in turn keeps your sales and profit statistics up to date. Cost adjustment forwards cost changes from inbound entries, such as purchases or production output, to the related outbound entries, such as sales or transfers. The adjustment is helpful for new [!INCLUDE[prod_short](includes/prod_short.md)] customers and small businesses with relatively low inventory transaction levels. However, as a business grows and inventory levels increase, adjustments can slow down system performance. To minimize reduced performance during posting, select a time option to define how far back in time from the work date an inbound transaction can occur to potentially trigger adjustment of related outbound value entries. Alternatively, you can manually adjust costs at regular intervals with the **Adjust Cost - Item Entries** batch job. You can also set the **Automatic Cost Adjustment** field to **Never**. A notification displays from which you can start an assisted setup guide to help you schedule tasks for the job queue. To learn more, go to [Adjust Item Costs](inventory-how-adjust-item-costs.md).|
|**Expected Cost Posting to G/L**|Ensure that you post expected costs to the general ledger. The interim G/L accounts show an estimate of the amounts due and the cost of the traded items before you invoice them. To learn more, go to [Design Details: Expected Cost Posting](design-details-expected-cost-posting.md) and [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md).|
|**Average Cost Calc. Type**|Define if the average cost is to be calculated per item only or per item for each stockkeeping unit and for each variant of the item. To learn more, go to [Design details: average cost](design-details-average-cost.md).|
|**Average Cost Period**|Select the period of time you would like application to use for calculating the weighted average cost of items that use the average costing method. To learn more, go to [Design details: average cost](design-details-average-cost.md).|
|**Default Costing Method**|Select the default costing method that determines whether an actual or a budgeted value is capitalized and used in the cost calculation. You can select a different costing method for a specific item either by selecting item template where costing method is defined or by manually selecting a different value on the **Item Card** page. To learn more, go to [Design details: costing methods](design-details-costing-methods.md).|

To learn more about costing in general, go to [Managing Inventory Costs](finance-manage-inventory-costs.md).  

If you want to include warehouse handling times in the order promising calculation on purchase lines, you can set it up as a default for inventory on the **Inventory Setup** page, and for your location. To learn more, go to [Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md).  

## Allow workers to post transactions at the same time

To allow people to post inventory transactions at the same time, you can enable the **Enable multiple users to post item ledger entries and value entries at the same time** feature on the **Feature Management** page. By default, the feature isn’t enabled.

> [!NOTE]
> Similar features are available for project, resource, and warehouse entries. To learn more, go to:
>
> * [Allow multiple people to post project transactions at the same time](projects-how-setup-jobs.md#allow-multiple-people-to-post-project-transactions-at-the-same-time)
> * [Allow multiple people to post resource transactions at the same time](projects-how-setup-resources.md#allow-multiple-people-to-post-resource-transactions-at-the-same-time)
> * [Design details: Creating warehouse entries](design-details-warehouse-entries.md)

If you enable the feature, [!INCLUDE [prod_short](includes/prod_short.md)] assigns entry numbers for each table from `SequenceNumbers` in the database, which allows more people to post transactions at the same time. The result can be that sometimes inventory entries from two or more transactions are interleaved. For example, an item register might contain any or all of the entry tables, as shown in the following image.

:::image type="content" source="media/interleaved inventory tables.png" alt-text="Screenshot that shows the item register with several entry tables." lightbox="media/interleaved inventory tables.png":::

If you don’t enable the feature, when someone posts an inventory transaction the tables are locked and other users can’t post inventory transactions. [!INCLUDE [prod_short](includes/prod_short.md)] finds the last entry in each table and assigns a number that’s one higher. This numbering ensures that entries that belong to the same register are consecutive, but prevents other people from posting at the same time.

> [!NOTE]
> You might not want to enable the feature if you have a feature or extension that:
>
> - Relies on consecutive entry numbers.
> - Requires that tables are locked throughout the posting process.

## Related information

[Set Up Inventory](inventory-setup-inventory.md)  
[Manage Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
