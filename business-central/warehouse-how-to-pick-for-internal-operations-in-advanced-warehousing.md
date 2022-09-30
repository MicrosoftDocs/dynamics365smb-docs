---
    title: Pick for Internal Operations in Advanced Warehouse Configurations
    description: If your locations use picking and shipping, pick components for production, assembly, and job activities on the Warehouse Pick page.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/02/2022
    ms.author: bholtorf

---
# Pick for Production, Assembly, or Jobs in Advanced Warehouse Configurations

In advanced warehouse configurations where the location is set up to use picking and shipping, you can pick components for production and assembly activities on the **Warehouse Pick** page.  

You can also use the **Movement Worksheet** page to spontaneously move items between bins without reference to a source document. For more information, see [Move Items in advanced warehouse configurations](warehouse-how-to-move-items-in-advanced-warehousing.md).  

For information about picking items in basic warehouse locations that are set up for picking only, see [Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).  

> [!NOTE]
> You can't create a warehouse pick document from scratch because a pick activity is always part of a workflow, either in a pull or a push scenario.  

You can create the warehouse pick document in a push fashion by selecting **Create Whse. Pick** on the source document, such as a released assembly order or warehouse shipment. For more information, see [Pick Items with Warehouse Picks](warehouse-how-to-pick-items-for-warehouse-shipment.md).  

You can also create a warehouse pick document in a pull fashion by using the **Pick Worksheet** page to detect pick requests. This method is useful for shipment and internal operations. You can then create the required warehouse pick documents.  

The following procedure explains a pull scenario where you pick components for a released production order through the **Pick Worksheet** page. The procedure also applies for an assembly order.  

To create pick requests, both for pull and for push scenarios, the source documents in question must be released. Release source documents for internal operations in the following ways.  

|Source Document|Release Method|  
|---------------------|--------------------|  
|Production Order|Change order type to released production order.|  
|Assembly Order|Change status to Released.|
|Jobs | Change status to Open.|  

## To pick components using the pick worksheet

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Pick Worksheet**, and then choose the related link.  
2. Choose the **Get Warehouse Documents** action, and then select the component lines from the released production order.  
3. Sort the lines to ensure efficient picking. You might want to combine lines to save employee time.  
4. Choose the **Create Pick** action.  
5. Define how to create the warehouse pick documents and how to sort pick lines by filling fields on the **Create Pick** page.  
6. Choose the **OK** button. Warehouse pick documents are created with pick lines for each component that is required in the internal operation.  

Operation areas such as production shop floors might have a default bin for the components they require. If so, the default bin code is added to the warehouse pick document to indicate where to put the items. For more information, see the tooltips for the **To-Production Bin Code** or the **To-Assembly Bin Code** fields.

## Filling the Consumption Bin

This flow chart shows how the **Bin Code** field on production order component lines is filled according to your location setup.

![Bin flow chart.](media/binflow.png "BinFlow")  

## See related [Microsoft training](/training/paths/pick-ship-items-business-central/)

## See also

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
