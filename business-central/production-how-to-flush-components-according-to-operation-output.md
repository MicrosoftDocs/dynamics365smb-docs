---
    title: Flush Components According to Operation Output
    description: For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to Finished.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Flush Components According to Operation Output
You can define different flushing strategies, to automate registering of consumption of components. 

For example, if a production order to produce 800 meters requires 8 kg of a component, then when you post 200 meters as output, 2 kg are automatically posted as consumption. 

This functionality is useful for the following reasons:  

- **Inventory Valuation**

    Value entries for output and consumption are created in parallel as the production order progresses. Without routing link codes, the inventory value will increase as output is posted and then decrease at a later point in time when the value of component consumption is posted together with the finished production order.  
- **Inventory Availability**

    With gradual consumption posting, the availability of component items is more up-to-date, which is important to maintain the internal balance between demand and supply. Without routing link codes, other demands for the component may believe that it is available as long as it is pending a delayed consumption posting.  
- **Just-in-Time**

    With the ability to customize products to customer requests, you can minimize waste by making sure that work and system changes only occur when it is necessary.  

You can achieve that by combining backward flushing method and routing link codes so that the quantity that is flushed for each operation is proportional to the actual output of the finished operation. For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to **Finished**. If you also define routing link codes, then calculation and posting occurs when each operation is finished, and the quantity that was actually consumed in the operation is posted. For more information, see [Create Routings](production-how-to-create-routings.md).  

## To flush components according to operation output

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Choose the **Edit** action.  
3.  On the **Replenishment** FastTab, in the **Flushing Method** field, select **Backward**.  

    > [!NOTE]  
    >  Select **Pick + Backward** if the component is used in a location that is set up for directed put-away and pick.  

4.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
5.  Define routing link codes for every operation that consumes the component. For more information, see [Create Routings ](production-how-to-create-routings.md).  
    > [!IMPORTANT]  
    > Do not use same routing routing link for different operations in the routing, as it will lead to registration of consumption of component for each linked operation.  
6.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.  
7.  Define routing link codes from each instance of the component to the operation where it is consumed.

The consumption will be posted automatically when you register output. For more information, see [Batch Post Output and Run Times](production-how-to-post-output-quantity.md)

## Flushing methods

The following table describes the available flushing method options that you can specify on **Item** cards and **Stockkeeping Unit** cards.

|Option|Description|
|------------|-------------|  
|Manual|Requires that you manually enter and post consumption in the consumption journal.|
|Forward|Automatically posts consumption according to the production order component lines. <br><br>By default, the posting of component consumption occurs when you change the status of a production order to **Released**. However, if you use the **Routing Link** Code field on production order component lines, then posting occurs per operation when the operation starts. For more information, see [How to: Create Routing Links](production-how-to-create-routings.md#to-create-routing-links). <br><br> **Note**<br>For forward flushing, the operation-specific posting that you obtain with routing link codes is based on the expected quantity that is defined on the component line. For information about operation-specific flushing based on actual output, see the description of **Backward** in this topic.<br><br>If the location or resources where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**. For more information, see [How to: Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md). <br><br> **Important** <br>Forward flushing also occurs when you choose **Refresh** on a released production order that was created from scratch. On these directly created released production orders, you cannot change bin information because the production order component lines are generated when you refresh the order, which at the same time forward flushes the components. Therefore, if you want to change bin information on production order component lines before forward flushing occurs, then that order must be created with the *Planned* or *Firm Planned* status.|
|Backward|Automatically calculates and posts consumption according to the production order component lines.<br><br> By default, the calculation and posting of component consumption occurs when you change the status of a released production order to **Finished**. However, if you use the **Routing Link Code** field on the production order component lines, then calculation and posting occurs when each operation is finished.<br><br> **Note** <br>Backward flushing and routing link codes can be combined so that the quantity that is flushed per operation is proportional to the actual output of that operation. For more information, see [How to: Flush Components According to Operation Output](#to-flush-components-according-to-operation-output).<br><br> If the location or machine center where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**.|
|Pick + Forward|Same as for Forward flushing method, except it only works for locations that use directed put-away and pick.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component has been picked from the warehouse.<br><br> **Note** <br>If a component is set up with the Pick + Forward flushing method, then it cannot have a routing link code to an operation that is set up with the forward flushing method. The component would then be automatically flushed when the operation starts, which makes it impossible to request the pick activity.|
|Pick + Backward|Same as for Backward flushing method, except it only works for locations that use directed put-away and pick.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component has been picked from the warehouse.|

## See Also

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
