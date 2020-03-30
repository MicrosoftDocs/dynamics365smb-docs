---
    title: How to Pick for Internal Operations in Advanced Warehouse Configurations | Microsoft Docs
    description: In advanced warehouse configurations where the location is set up to use picking as well as shipping, you can pick components for production and assembly activities with the **Warehouse Pick** page.
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
# Pick for Production or Assembly in Advanced Warehouse Configurations
In advanced warehouse configurations where the location is set up to use picking as well as shipping, you can pick components for production and assembly activities with the **Warehouse Pick** page.  

Alternatively, you can use the **Movement Worksheet** page to move items between bins ad hoc, meaning without reference to a source document. For more information, see [Move Items in advanced warehouse configurations](warehouse-how-to-move-items-in-advanced-warehousing.md).  

For information about picking items for internal operations in basic warehouse locations that are set up for picking only, see [Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).  

You cannot create a warehouse pick document from scratch because a pick activity is always part of a workflow, either in a pull or a push scenario.  

You can create the warehouse pick document in a push fashion by selecting **Create Whse. Pick** on the source document, such as a released assembly order or warehouse shipment. For more information, see [Pick Items with Warehouse Picks](warehouse-how-to-pick-items-for-warehouse-shipment.md).  

Alternatively, you can create the warehouse pick document in a pull fashion by using the **Pick Worksheet** page to detect pick requests, both for shipment and internal operations, and then create the required warehouse pick documents.  

The following procedure explains a pull scenario where you pick components for a released production order through the **Pick Worksheet** page. The procedure also applies for an assembly order.  

To create pick requests, both for pull and for push scenarios, the source documents in question must be released. Release source documents for internal operations in the following ways.  

|Source Document|Release Method|  
|---------------------|--------------------|  
|Production Order|Change order type to released production order.|  
|Assembly Order|Change status to Released.|  

## To pick components using the pick worksheet  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Pick Worksheet**, and then choose the related link.  
2.  Choose the **Get Warehouse Documents** action, and then select the component lines from the released production order.  
3.  Inspect the lines, sort them to ensure an efficient picking round, and combine them with other worksheet lines if necessary to make best use of employee time.  
4.  Choose the **Create Pick** action.  
5.  Define how to create the warehouse pick documents and how to sort pick lines by filling fields on the **Create Pick** page.  
6.  Choose the **OK** button. Warehouse pick documents are created with pick lines for each component that is required in the internal operation.  

If the internal operation area, such as a production shop floor, is set up with a default bin for placement of components to be used in the operation, then that bin code is inserted in the Place lines on the warehouse pick document to instruct warehouse workers where to place the items. For more information, see the **To-Production Bin Code** or the **To-Assembly Bin Code** field.

## Filling the Consumption Bin
This flow chart shows how the **Bin Code** field on production order component lines is filled according to your location setup.

![Bin flow chart](media/binflow.png "BinFlow")  

## See Also
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
