---
title: Put away production output
description: This article describes how to put away your production output.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 03/12/2025
ms.custom: bap-template
ms.search.forms: 9326, 99000831, 9315, 7375
---
# Put away production or assembly output

How you put away your output from production depends on how your warehouse is set up as a location. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

In a basic warehouse configuration for the inbound flow (put-away), on the **Location Card** page for the location, activate following settings:

* For production, in the **Prod. Output Whse. Handling** field, select **Inventory Put-away**.
* Assembly processes don't support inventory put-aways. You post an assembly order to register output. If you use bins, you can move items between the bins later. Learn more at [Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).  
* For projects, put-away isn't applicable.

In advanced warehouse configurations where a location requires put-away, create an internal put-away, a movement, or a warehouse put-away to put away the output.  

## Put away production output with an inventory put-away

The first step to put away output is to create the inbound warehouse request. This request informs the warehouse that the production or assembly order output is ready to be put away.

### To create the inbound warehouse request  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Released Production Order**, and then choose the related link.  
2. Choose the production order that's ready for put-away, and then choose the **Create Inbound Whse. Request** action.  

> [!NOTE]  
> You can also create the inbound warehouse request by choosing the **Create Inbound Request** field when you refresh the production order. Learn more at [Refresh or Replan Production Orders](production-how-to-replan-refresh-production-orders.md).  

### To put away output with an inventory put-away  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Inventory Put-away**, and then choose the related link.  
2. Create a new inventory put-away. Learn more at [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).
3. To access the production order output, choose the **Get Source Documents** action, and then select the released production order.  
4. Fill in the put-away lines as needed.
5. When the lines are ready for posting, choose the **Post** action. Posting creates the warehouse entries and posts the output of the items.  

    [!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

You can also create an **Inventory Put-away** directly from the released production order. Learn more at [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).  

When you post an inventory put-away, [!INCLUDE [prod_short](includes/prod_short.md)] assumes that all the operations are posted according to the standard routing. That is, the output quantity is posted according to the last operation. You can use the output journal to post variances in the output quantity and the setup and run times. If you must post partially after you created the inventory put-away, you can do so on set-up times and quantities for all operations except the last one. The inventory put-away controls the last operation.  

If you only need to post the set-up or run time on the last operation, set the output quantity on the last operation to 0. You can choose not to post the last line at all by deleting it.

## To put away assembly and production output in advanced warehouse configurations

When you post output for a production or assembly order in advanced warehouse configurations, the output goes to the bin defined in the production or assembly order. To learn more about different ways to move items in the warehouse with advanced configurations, go to [Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md#to-move-items-with-the-warehouse-movement-worksheet).

> [!NOTE]  
> You can't enter the number of the source document, such as the production order number, in internal put-away or movement documents for assembly or production output.  

You can also use warehouse put-aways for production outputs, which means you can use the same warehouse process for production outputs as you use for other receipts. Using the same process makes things easier because you don't have to switch between different types of document. Also, it's especially valuable for advanced configurations where Directed Put-Away and Pick is enabled because inventory put-away documents aren't available.

To use warehouse put-aways, on the **Location Card** page, in the **Prod. Output Whse. Handling** field, choose **Warehouse Put-away**.

> [!NOTE]
> For locations where Directed Put-away and Pick is enabled, make the field editable and allow the selection of **No warehouse handling** or **Warehouse put-away**. You can't select the **Inventory Put-away** option.
>
> You can't activate warehouse put-away if there are released production orders for the selected location.

When you post production output for a location where the **Prod. Output Whse. Handling** field is set to **Warehouse Put-away** on the **Location Card** page, the warehouse put-away document is either created automatically or you must use the **Warehouse Put-Away Worksheet** page.

If you delete a warehouse put-away, you can manually create a new one using the **Create warehouse put-away** action on the **Release Production Order** or **Finished Prod Order** pages.

> [!NOTE]
> You can't have production order lines with different locations with **Prod. Output Whse. Handling** set to **Warehouse Put-away**. To resolve this issue, use different production orders.
>
> You can't cancel output if there are outstanding or completed put-aways.

## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
