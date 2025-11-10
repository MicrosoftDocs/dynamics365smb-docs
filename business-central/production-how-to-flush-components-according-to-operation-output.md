---
title: Flush components according to operation output
description: This article describes how to flush components according to operation output and other flushing methods involved.
author: brentholtorf
ms.topic: how-to
ms.search.keywords:
ms.date: 11/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Flush components according to operation output

You can define different flushing strategies to automate the registration of consumption of components.

This feature is useful for the following reasons:  

- **Inventory Valuation**

    Value entries for output and consumption are created in parallel as the production order progresses. Without routing link codes, the inventory value increases as output is posted and decreases later when you post the consumption with the finished production order.  
- **Inventory Availability**

    With gradual consumption posting, the availability of component items is more up-to-date, which is important to maintain the internal balance between demand and supply. Without routing link codes, other demands for the component might believe that it's available as long as it's pending a delayed consumption posting.  
- **Just-in-Time**

    With the ability to customize products to customer requests, you can minimize waste by making sure that work and system changes only occur when it's necessary.  

- **Reduce data entry**

    The ability to automatically flush an operation lets you automate the entire process of recording consumption and output. The disadvantage of using automatic flushing is that you might not accurately record, or even be aware of, scrap.

## Automatic consumption posting (flushing) methods  

- Forward Flush the Entire Order  
- Forward Flushing by Operation  
- Back Flushing by Operation  
- Back Flushing the Entire Order  

### Forward flush an entire order  

Forward flushing a production order at the start of the job is similar to a manual consumption. The significant difference is that consumption happens automatically.  

- The entire contents of the production BOM are consumed and deducted from inventory at the time the released production order is refreshed.  
- The consumption quantity is the quantity per assembly stated on the production BOM, multiplied by the number of parent items you're building.  
- There's no need to record any information in the consumption journal if all of the items are to be flushed.  
- When you consume items from inventory, it doesn't matter when output journal entries are made because the output journal has no effect on this mode of consumption posting.  
- No routing link codes can be set.  

Forward flushing an entire order is suited in production environments with:  

- A low number of defects.  
- A low number of operations.  
- High component consumption in early operations.  

### Forward flushing by operation  

Flushing by operation allows you to deduct inventory during a specific operation in the routing of the parent item. Material is tied to the routing using routing link codes, which correspond to routing link codes applied to components in the production BOM.  

The flush takes place when the operation that has the same routing link code is started. Started means that some activity is recorded in the output journal for that operation. And that activity might just be that a setup time is entered.  

The amount of the flush is for the quantity per assembly on the production BOM multiplied by the number of parent items you're building (expected quantity).  

This technique is best employed when there are many operations and certain components aren't needed until late in the assembly sequence. In fact, a Just-in-Time (JIT) setup might not even have the items on hand when the RPO is begun.  

Material can be consumed during operations by using routing link codes. Some components might not be used until final assembly operations and shouldn't be withdrawn from stock until that time.  

### Back flushing by operation  

Back flushing by operation records consumption after the operation is posted in the output journal.  

The advantage of this method is that the number of parent parts finished in the operation is known.  

Material in the production BOM is linked to the routing records using routing link codes. The back flush takes place when an operation with a particular routing link code is posted with a finished quantity.  

The amount is the quantity per assembly on the production BOM multiplied by the number of parent items posted as output for the operation. This quantity might be different than the expected quantity.  

### Back flushing an entire order  

This reporting method doesn't consider routing link codes.  

No components are picked until the released production order status is changed to *Finished*. The amount is the quantity per assembly on the production BOM multiplied by the number of parent items that you finished and put in inventory.  

Backward flushing the entire production order requires the same setup as for forward flushing: The reporting method must be set to backward on each item card for all items within the parent BOM to be reported. In addition, all routing link codes must be removed from the production BOM. 

For example, if a production order to produce 800 meters requires 8 kg of a component, then when you post 200 meters as output, 2 kg are automatically posted as consumption.

You can achieve that by combining backward flushing method and routing link codes so that the quantity that is flushed for each operation is proportional to the actual output of the finished operation. For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to **Finished**. If you also define routing link codes, then calculation and posting occurs when each operation is finished, and the quantity that was consumed in the operation is posted. For more information, see [Create Routings](production-how-to-create-routings.md).  

## To flush components according to operation output

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then choose the related link.  
2. Choose the **Edit** action.  
3. On the **Replenishment** FastTab, in the **Flushing Method** field, select **Backward**.  

    > [!NOTE]  
    > Select **Pick + Backward** if the component is used in a location that is set up for directed put-away and pick.  

4. [!INCLUDE[open-search](includes/open-search.md)], enter **Routings**, and then choose the related link.  
5. Define routing link codes for every operation that consumes the component. For more information, see [Create Routings](production-how-to-create-routings.md).  
    > [!IMPORTANT]  
    > Don't use the same routing link for different operations in the routing. Using the same routing link would lead to registration of consumption of component for each linked operation.  
6. [!INCLUDE[open-search](includes/open-search.md)], enter **Production BOM**, and then choose the related link.  
7. Define routing link codes from each instance of the component to the operation that consumes it.

The consumption is posted automatically when you register output. To learn more, go to [Batch Post Output and Run Times](production-how-to-post-output-quantity.md).

## Flushing methods

The following table describes the flushing method options that you can specify on **Item** cards and **Stockkeeping Unit** cards.

|Option|Description|
|------------|-------------|  
|Manual|You can manually consume items without picking. For each item, stockkeeping unit, or production order component line you can ignore the **Prod. Consumption Whse. Handling** setting in the **Location Card** page. Skipping warehouse or inventory picks is typical for automatic flushing methods, such as **Backward** and **Forward**. It might be useful for components which, due to their nature, you store in the shop floor zone so there's no need to pick. However, they might require manual posting of consumption, for example, because the consumed quantity can very or they require item tracking.<br><br>To start using this feature, on the **Feature Management** page, activate **Feature Update: 'Manual' flushing method without requiring pick**. Existing records upgrade from **Manual** to the **Pick + Manual** flushing method. The **Pick + Manual** option is added immediately and works, regardless of whether you enable the feature key. If the feature isn't enabled, **Manual** and **Pick + Manual** both require picking due to the original behavior. When the feature key is enabled, the **Manual** option doesn't require picking.|
|Forward|Automatically posts consumption according to the production order component lines. <br><br>By default, the posting of component consumption occurs when you change the status of a production order to **Released**. However, if you use the **Routing Link** Code field on production order component lines, then posting occurs per operation when the operation starts. For more information, see [How to: Create Routing Links](production-how-to-create-routings.md#to-create-routing-links). <br><br> **Note**<br>For the forward flushing option, the operation-specific posting that you get with routing link codes is based on the expected quantity that is defined on the component line. For information about operation-specific flushing based on actual output, see the description of **Backward** in this article.<br><br>If the location or resources where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**. For more information, see [How to: Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md). <br><br> **Important** <br>Forward flushing also occurs when you choose **Refresh** on a released production order that was created from scratch. On the released production orders, you can't change bin information because you generate the production order component lines when you refresh the order. Refreshing the order forward flushes the components. Therefore, if you want to change bin information on production order component lines before forward flushing occurs, then that order must be created with the *Planned* or *Firm Planned* status.|
|Backward|Automatically calculates and posts consumption according to the production order component lines.<br><br> By default, the calculation and posting of component consumption occurs when you change the status of a released production order to **Finished**. However, if you use the **Routing Link Code** field on the production order component lines, then calculation and posting occurs when each operation is finished.<br><br> **Note** <br>Backward flushing and routing link codes can be combined so that the quantity that is flushed per operation is proportional to the actual output of that operation. For more information, see [How to: Flush Components According to Operation Output](#to-flush-components-according-to-operation-output).<br><br> If the location or machine center where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**.|
|Pick + Forward|Same as for Forward flushing method, except it only works for locations that use either advanced warehouse configuration or basic warehouse configuration with mandatory bins.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component is picked in the warehouse.<br><br> **Note** <br>If a component uses the Pick + Forward flushing method, it can't have a routing link code to an operation that uses the forward flushing method. The component would then be automatically flushed when the operation starts, which makes it impossible to request the pick activity.|
|Pick + Backward|Same as for Backward flushing method, except it only works for locations use either advanced warehouse configuration or basic warehouse configuration with mandatory bins.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component is picked in the warehouse.|
|Pick + Manual|Require picking if consumption needs to happen at a location where warehouse handling is enabled.|

## Related information

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
