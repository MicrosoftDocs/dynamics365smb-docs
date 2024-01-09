---
title: Set Up General Inventory Information
description: Describes how to define the general inventory setup so that you can manage your warehouse and stock.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.search.form: 30, 456, 461
ms.date: 07/28/2021
ms.author: bholtorf

---
# Set Up General Inventory Information

You specify your general inventory setup on the **Inventory Setup** page.

## To set up general inventory information

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. On the **Inventory Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

For detailed information about the costing fields, **Automatic Cost Posting**, **Expected Cost Posting to G/L**, and **Default Costing Method**, see [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md), [Design Details: Inventory Costing](design-details-inventory-costing.md), and [Design Details: Expected Cost Posting](design-details-expected-cost-posting.md). For more information about costing in general, see [Managing Inventory Costs](finance-manage-inventory-costs.md).  

If you want to include warehouse handling time in the order promising calculation on the purchase line, you can set it up as a default for the inventory, on the **Inventory Setup** page, and for your location. For more information, see [Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md).  

> [!NOTE]
> The **Automatic Cost Adjustment** field is set to *Always* by default to ensure that inventory values are always correct in the general ledger, which in turn keeps your sales and profit statistics up to date. Cost changes from inbound entries, such as those for purchases or production output, are assigned to the related outbound entries, such as sales or transfers. This is helpful for new [!INCLUDE[prod_short](includes/prod_short.md)] customers and small businesses with relatively low inventory transaction levels.
>
> However, as a business grows and inventory levels increase, this can slow down system performance. To minimize reduced performance during posting, select a time option to define how far back in time from the work date an inbound transaction can occur to potentially trigger adjustment of related outbound value entries.
>
> Alternatively, you can manually adjust costs at regular intervals with the Adjust Cost - Item Entries batch job. You can also turn off automatic cost posting or set the **Automatic Cost Adjustment** field to *Never*. In both cases, a notification displays from which you can start an assisted setup guide to help you schedule tasks for the job queue. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## See Also

[Set Up Inventory](inventory-setup-inventory.md)  
[Design Details: Costing Methods](design-details-costing-methods.md)  
[Manage Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]