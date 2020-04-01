---
    title: How to Flush Components According to Operation Output | Microsoft Docs
    description: For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to **Finished**. For more information, see Flushing Method.
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
# Flush Components According to Operation Output
For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to **Finished**.  

If you also define routing link codes, then calculation and posting occurs when each operation is finished, and the quantity that was actually consumed in the operation is posted. For more information, see [Create Routings](production-how-to-create-routings.md).  

For example, if a production order to produce 800 meters requires 8 kg of a component, then when you post 200 meters as output, 2 kg are automatically posted as consumption.  

This functionality is useful for the following reasons:  

-   **Inventory Valuation** - Value entries for output and consumption are created in parallel as the production order progresses. Without routing link codes, the inventory value will increase as output is posted and then decrease at a later point in time when the value of component consumption is posted together with the finished production order.  
-   **Inventory Availability** - With gradual consumption posting, the availability of component items is more up-to-date, which is important to maintain the internal balance between demand and supply. Without routing link codes, other demands for the component may believe that it is available as long as it is pending a delayed consumption posting.  
-   **Just-in-Time** – With the ability to customize products to customer requests, you can minimize waste by making sure that work and system changes only occur when it is necessary.  

The following procedure shows how to combine backward flushing and routing link codes so that the quantity that is flushed for each operation is proportional to the actual output of the finished operation.  

## To flush components according to operation output  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Choose the **Edit** action.  
3.  On the **Replenishment** FastTab, in the **Flushing Method** field, select **Forward**.  

    > [!NOTE]  
    >  Select **Pick+ Forward** if the component is used in a location that is set up for directed put-away and pick.  

4.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
5.  Define routing link codes for every operation that consumes the component. For more information, see [Create Routings ](production-how-to-create-routings.md).  
6.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.  
7.  Define routing link codes from each instance of the component to the operation where it is consumed.

    > [!IMPORTANT]  
    >  The component must have a routing link to the last operation in the routing.  

## See Also  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
