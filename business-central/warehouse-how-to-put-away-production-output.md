---
title: Put Away Production Output
description: This article describes how to put away your production output.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/20/2022
ms.custom: bap-template
ms.search.forms: 9326, 99000831, 9315, 7375
---
# Put Away Production or Assembly Output

How you put away your output from production depends on how your warehouse is set up as a location. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

In a basic warehouse configuration for the inbound flow (put-away), on the **Location Card** page for the location, activate following settings:

* Production, select the *Inventory Put-away* in the **Prod. Output Whse. Handling** field.
* Assembly processes don't support inventory put-aways. You post an assembly order to register output. If you use bins, you can move items between the bins later. Learn more at [Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).  
* Projects, put-away is not applicable for projects.

In advanced warehouse configurations where a location requires both put-away, create either an internal put-away document or a movement document to put away the output.  

## To put away production output with an inventory put-away

The first step to put away output is to create the inbound warehouse request. This request informs the warehouse that the production or assembly order output is ready to be put away.

### To create the inbound warehouse request  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Order**, and then choose the related link.  
2. Choose the production order that's ready for put-away, and then choose the **Create Inbound Whse. Request** action.  

> [!NOTE]  
> You can also create the inbound warehouse request by choosing the **Create Inbound Request** field when you refresh the production order. Learn more at [Refresh or Replan Production Orders](production-how-to-replan-refresh-production-orders.md).  

### To put output away with an inventory put-away  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-away**, and then choose the related link.  
2. Create a new inventory put-away. Learn more at [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).
3. To access the production order output, choose the **Get Source Documents** action, and then select the released production order.  
4. Fill in the put-away lines as needed.
5. When the lines are ready for posting, choose the **Post** action. Posting will create the warehouse entries and post the output of the items.  

    [!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

You can also create an **Inventory Put-away** directly from the released production order. Learn more at [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).  

When you post an inventory put-away, it's assumed that all the operations are posted according to the standard routing. That is, the output quantity is posted according to the last operation. You can use the output journal to post variances in the output quantity and the setup and run times. If you must post partially after you created the inventory put-away, you can do so on set up times and quantities for all operations except the last one. The last operation is controlled by the inventory put-away.  

If you only need to post set up or run time on the last operation, set the output quantity on the last operation to 0. You can choose not to post the last line at all by simply deleting it.

## To put assembly and production output away in advanced warehouse configurations

When you post the output of production or assembly order in a warehouse that uses directed put-away and pick, the output is placed in the bin defined in the production or assembly order. Learn more about different ways to move items in the warehouse with advanced configurations, go to [Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md#to-move-items-with-the-warehouse-movement-worksheet).

> [!NOTE]  
> You can't enter the source document number, such as the production order number, in the internal put-away, put-away, or movement documents for assembly or production output processes.  

## See Also  

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
