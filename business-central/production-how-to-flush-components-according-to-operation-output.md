---
    title: Flush Components According to Operation Output
    description: This topic describes how to flush components according to operation output as well as other flushing methods involved.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/22/2021
    ms.author: bholtorf

---
# Flush Components According to Operation Output
You can define different flushing strategies, to automate registering of consumption of components. 

This functionality is useful for the following reasons:  

- **Inventory Valuation**

    Value entries for output and consumption are created in parallel as the production order progresses. Without routing link codes, the inventory value will increase as output is posted and then decrease at a later point in time when the value of component consumption is posted together with the finished production order.  
- **Inventory Availability**

    With gradual consumption posting, the availability of component items is more up-to-date, which is important to maintain the internal balance between demand and supply. Without routing link codes, other demands for the component may believe that it is available as long as it is pending a delayed consumption posting.  
- **Just-in-Time**

    With the ability to customize products to customer requests, you can minimize waste by making sure that work and system changes only occur when it is necessary.  

- **Reduce data entry**

    With the ability to automatically flush an operation, the entire consumption and output recording process can be automated. The disadvantage of using automatic flushing is that you may not be accurately recording, or even aware of, scrap.

## Automatic Consumption Posting (Flushing) methods  

- Forward Flush the Entire Order  
- Forward Flushing by Operation  
- Back Flushing by Operation  
- Back Flushing the Entire Order  

### Automatic Reporting - Forward Flush the Entire Order  
If you forward flush the production order at the start of the job, the behavior of application is very similar to a manual consumption. The major difference is that consumption happens automatically.  

- The entire contents of the production BOM are consumed and deducted from inventory at the time the released production order is refreshed.  
- The consumption quantity is the quantity per assembly stated on the production BOM, multiplied by the number of parent items you are building.  
- There is no need to record any information in the consumption journal if all of the items are to be flushed.  
- When consuming items from inventory, it does not matter when output journal entries are made, because the output journal has no effect on this mode of consumption posting.  
- No routing link codes can be set.  

Forward flushing an entire order is suited in production environments with:  

-   A low number of defects  
-   A low number of operations  
-   High component consumption in early operations  

### Automatic Reporting - Forward Flushing by Operation  
Flushing by operation allows you to deduct inventory during a specific operation in the routing of the parent item. Material is tied to the routing using routing link codes, which correspond to routing link codes applied to components in the production BOM.  

The flush takes place when the operation that has the same routing link code is started. Started means that some activity is recorded in the output journal for that operation. And that activity might just be that a setup time is entered.  

The amount of the flush is for the quantity per assembly stated on the production BOM multiplied by the number of parent items being built (expected quantity).  

This technique is best employed when there are many operations and certain components are not needed until late in the assembly sequence. In fact, a Just-in-Time (JIT) setup might not even have the items on hand when the RPO is begun.  

Material can be consumed during operations by using routing link codes. Some components may not be used until final assembly operations and should not be withdrawn from stock until that time.  

### Automatic Reporting - Back Flushing by Operation  
Back flushing by operation records consumption after the operation is posted in the output journal.  

The advantage of this method is that the number of parent parts finished in the operation is known.  

Material in the production BOM is linked to the routing records using routing link codes. The back flush takes place when an operation with a particular routing link code is posted with a finished quantity.  

The amount of the flush is for the quantity per assembly stated on the production BOM multiplied by the number of parent items that were posted as output quantity at that operation. This might be different from the expected quantity.  

### Automatic Reporting - Back Flushing the Entire Order  
This reporting method does not consider routing link codes.  

No components are picked until the released production order status is changed to *Finished*. The amount of the flush is the quantity per assembly stated on the production BOM multiplied by the number of parent items that were finished and placed into inventory.  

Backward flushing the entire production order requires the same setup as for forward flushing: The reporting method must be set to backward on each item card for all items within the parent BOM to be reported. In addition, all routing link codes must be removed from the production BOM. 



For example, if a production order to produce 800 meters requires 8 kg of a component, then when you post 200 meters as output, 2 kg are automatically posted as consumption. 
You can achieve that by combining backward flushing method and routing link codes so that the quantity that is flushed for each operation is proportional to the actual output of the finished operation. For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to **Finished**. If you also define routing link codes, then calculation and posting occurs when each operation is finished, and the quantity that was actually consumed in the operation is posted. For more information, see [Create Routings](production-how-to-create-routings.md).  

## To flush components according to operation output

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Choose the **Edit** action.  
3.  On the **Replenishment** FastTab, in the **Flushing Method** field, select **Backward**.  

    > [!NOTE]  
    >  Select **Pick + Backward** if the component is used in a location that is set up for directed put-away and pick.  

4.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
5.  Define routing link codes for every operation that consumes the component. For more information, see [Create Routings ](production-how-to-create-routings.md).  
    > [!IMPORTANT]  
    > Do not use same routing routing link for different operations in the routing, as it will lead to registration of consumption of component for each linked operation.  
6.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.  
7.  Define routing link codes from each instance of the component to the operation where it is consumed.

The consumption will be posted automatically when you register output. For more information, see [Batch Post Output and Run Times](production-how-to-post-output-quantity.md)

## Flushing methods

The following table describes the available flushing method options that you can specify on **Item** cards and **Stockkeeping Unit** cards.

|Option|Description|
|------------|-------------|  
|Manual|Requires that you manually enter and post consumption in the consumption journal.|
|Forward|Automatically posts consumption according to the production order component lines. <br><br>By default, the posting of component consumption occurs when you change the status of a production order to **Released**. However, if you use the **Routing Link** Code field on production order component lines, then posting occurs per operation when the operation starts. For more information, see [How to: Create Routing Links](production-how-to-create-routings.md#to-create-routing-links). <br><br> **Note**<br>For forward flushing, the operation-specific posting that you obtain with routing link codes is based on the expected quantity that is defined on the component line. For information about operation-specific flushing based on actual output, see the description of **Backward** in this topic.<br><br>If the location or resources where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**. For more information, see [How to: Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md). <br><br> **Important** <br>Forward flushing also occurs when you choose **Refresh** on a released production order that was created from scratch. On these directly created released production orders, you cannot change bin information because the production order component lines are generated when you refresh the order, which at the same time forward flushes the components. Therefore, if you want to change bin information on production order component lines before forward flushing occurs, then that order must be created with the *Planned* or *Firm Planned* status.|
|Backward|Automatically calculates and posts consumption according to the production order component lines.<br><br> By default, the calculation and posting of component consumption occurs when you change the status of a released production order to **Finished**. However, if you use the **Routing Link Code** field on the production order component lines, then calculation and posting occurs when each operation is finished.<br><br> **Note** <br>Backward flushing and routing link codes can be combined so that the quantity that is flushed per operation is proportional to the actual output of that operation. For more information, see [How to: Flush Components According to Operation Output](#to-flush-components-according-to-operation-output).<br><br> If the location or machine center where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**.|
|Pick + Forward|Same as for Forward flushing method, except it only works for locations that use either advanced warehouse configuration or basic warehouse configuration with mandatory bins.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component has been picked from the warehouse.<br><br> **Note** <br>If a component is set up with the Pick + Forward flushing method, then it cannot have a routing link code to an operation that is set up with the forward flushing method. The component would then be automatically flushed when the operation starts, which makes it impossible to request the pick activity.|
|Pick + Backward|Same as for Backward flushing method, except it only works for locations use either advanced warehouse configuration or basic warehouse configuration with mandatory bins.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component has been picked from the warehouse.|

## See Also

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
