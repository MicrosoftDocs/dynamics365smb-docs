---
    title: How to: Set Up Basic Warehouses with Operations Areas | Microsoft Docs
    description: If internal operation areas such as production or assembly exist in basic warehouse configurations where locations use the **Bin Mandatory** setup field and possibly the **Require Pick** and **Require Put-away** setup fields, then you can use the following basic warehouse documents to record your warehouse activities for internal operation areas:
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up Basic Warehouses with Operations Areas
If internal operation areas such as production or assembly exist in basic warehouse configurations where locations use the **Bin Mandatory** setup field and possibly the **Require Pick** and **Require Put-away** setup fields, then you can use the following basic warehouse documents to record your warehouse activities for internal operation areas:  
  
-   **Inventory Movement** window.  
  
-   **Inventory Pick** window.  
  
-   **Inventory Put-away** window.  
  
 To use these windows with internal operations, such as to pick and move components to production, you must make some or all the following setup steps depending on how much control you need:  
  
-   Enable the inventory pick, move, and put-away documents.  
  
-   Define default bin structures for components and end items flowing to and from operation resources.  
  
-   Make to- and from- bins that are dedicated to specific operation resources to prevent the items from being picked for outbound documents.  
  
 The following procedures are based on setting up basic warehouse activities around a production area. The steps are similar for other operation areas, such as assembly, service management, and jobs.  
  
> [!NOTE]  
>  In the following procedure, the **Bin Mandatory** setup field on location cards is selected as a precondition because that is considered the foundation for any level of warehouse management.  
  
### To enable inventory documents for internal operation activities  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link. Open the location card you want to update.  
  
2.  On the **Warehouse** FastTab, select the **Require Put-away** field to indicate that, when an inbound or internal source document with a bin code is released, an inventory put-away or an inventory movement document can be created.  
  
3.  Select the **Require Pick** field to indicate that when an outbound or internal source document with a bin code is created, an inventory pick or an inventory movement document must be created.  
  
### To define a default bin structure in the operation area  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link. Open the Location you want to update.  
  
2.  On the **Bins** FastTab, in the **Open Shop Floor Bin Code** field, enter the code of the bin in the production area with plenty of components that the machine operator can consume from without requesting a warehouse activity to bring them to the bin. Items that are placed in this bin are typically set up for automatic posting, or flushing. This means that the **Flushing Method** field contains **Forward** or **Backward**.  
  
3.  In the **To-Production Bin Code** field, enter the code of the bin in the production area where components that are picked for production at this location are placed by default before they can be consumed. Items that are placed in this bin are typically set up for manual consumption posting. This means that the **Flushing Method** field contains **Manual** or **Pick + Forward** or **Pick + Backward** for warehouse picks and inventory movements.  
  
    > [!NOTE]  
    >  When you use inventory picks, the **Bin Code** field on a production order component line defines the *take* bin from where components are decreased when posting consumption. When you use inventory movements, the **Bin Code** field on production order component lines defines the *place* bin in the operation area where the warehouse worker must place the components.  
  
4.  On the **Bins** FastTab, in the **From-Production Bin Code** field, enter the code of the bin in the production area where finished end items are taken from by default when the process involves a warehouse activity. In basic warehousing, the activity is recorded as an inventory put-away or an inventory movement.  
  
 Now, production order component lines with the default bin code require that forward-flushed components are placed there. However, until the components are consumed from that bin, other component demands may pick or consume from that bin because they are still considered available bin contents. To make sure that bin content is only available to component demand that uses that to-production bin, you must select the **Dedicated** field on the line for that bin code in the **Bins** window that you open from the location card.  
  
### To make dedicated component bins  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link. Select the location that you want to update.  
  
2.  On the **Navigate** tab, in the **Location** group, choose **Bins**.  
  
3.  Select the **Dedicated** field for each bin that you want to use exclusively for certain internal operations and where you want quantities to be reserved for that internal operation once placed there.  
  
    > [!NOTE]  
    >  The bin must be empty before you can select or clear the **Dedicated** field.  
  
## See Also  
 Bin Mandatory   
 Open Shop Floor Bin Code   
 To-Production Bin Code   
 Flushing Method   
 Bin Code   
 Dedicated   
 [How to: Move Components to an Operation Area in Basic Warehousing](../how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Pick for Production in Basic Warehousing](../how-to-pick-for-production-in-basic-warehousing.md)   
 [How to: Move Items Ad Hoc in Basic Warehousing](../how-to-move-items-ad-hoc-in-basic-warehousing.md)   
 [How to: Convert Existing Locations to Warehouse Locations](../how-to-convert-existing-locations-to-warehouse-locations.md)