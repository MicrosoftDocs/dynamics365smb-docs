---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Pick for Production in Basic Warehousing
When your warehouse location requires pick processing but does not require shipment processing, use the **Inventory Pick** window to organize and record the picking of components.  
  
> [!NOTE]  
>  In advanced warehouse configurations where locations require both picks and shipments you use warehouse picks to bring components to production orders.  
  
 In basic warehouse configurations, you can also pick for production with the **Inventory Movement** window.  
  
> [!NOTE]  
>  The following important differences exist between inventory picks and inventory movements:  
>   
>  -   When you register an inventory pick for an internal operation, such as production, the consumption of the picked components is posted at the same time. When you register an inventory movement for an internal operation, you only record the physical movement of the required components to a bin in the operation area without posting the consumption.  
> -   When you use inventory picks, the **Bin Code** field on a production order component line defines the *take* bin from where components are decreased when posting consumption. When you use inventory movements, the **Bin Code** field on production order component lines defines the *place* bin in the operation area where the warehouse worker must place the components.  
  
 A system precondition for picking, or moving, components for source documents is that an outbound warehouse request exists to notify the warehouse area of the component need. The outbound warehouse request is created whenever the production order status is changed to Released or when a released production order is created.  
  
### To pick components with the inventory pick document  
  
1.  In the **Search** box, enter **Inventory Picks**, and then choose the related link.  
  
2.  To access the production order components, on the **Actions** tab, in the **Functions** group, choose **Get Source Documents**, and then select the released production order.  
  
3.  Perform the pick, and then record the actual picking information in the **Inventory Pick** window.  
  
4.  When the lines are ready for posting, on the **Home** tab, in the **Process** group, choose **Post**. The posting creates the necessary warehouse entries and posts the consumption of the items.  
  
 You can also create an **Inventory Pick** directly from the released production order. On the **Actions** tab, in the **Warehouse** group, choose **Create Inventory Put-away\/Pick\/Movement**, and then select the **Create Invt. Pick** field on the **Options** FastTab of the request window. You can print the pick list by selecting the **Print Document** field.  
  
## See Also  
 Inventory Pick   
 [How to: Pick for Internal Operations in Advanced Warehousing](../how-to-pick-for-internal-operations-in-advanced-warehousing.md)   
 Inventory Movement   
 [How to: Move Components to an Operation Area in Basic Warehousing](../how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Move Items Ad Hoc in Basic Warehousing](../how-to-move-items-ad-hoc-in-basic-warehousing.md)