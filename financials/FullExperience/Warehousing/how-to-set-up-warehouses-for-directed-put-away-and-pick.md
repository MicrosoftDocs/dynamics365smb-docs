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
# How to: Set Up Warehouses for Directed Put-away and Pick
Directed put\-away and pick gives you access to advanced warehousing features that can greatly enhance your efficiency and data reliability. In order to use this functionality, you must first set up a number of parameters in your warehouse location.  
  
 To use the directed put\-away and pick functionality, you must activate the functionality on the location card.  
  
### To activate directed put away and pick functionality  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Select the location where you want to use directed put\-away and pick. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Warehouse** FastTab, select the **Directed Put\-away and Pick** field.  
  
 You do not need to fill in any other fields on the location card until later in the setup process.  
  
> [!NOTE]  
>  You cannot set up the warehouse to use bins when the location has open item ledger entries.  
  
 The next step is to define the type of bins you want to operate. For more information, see [How to: Set Up Bin Types](../WarehouseActivities/how-to-set-up-bin-types.md). The bin type defines how to use a given bin when processing the flow of items through the warehouse. You can assign a bin type to both a zone and to a bin.  
  
 You can also define warehouse class codes, if the warehouse carries items that need various storage conditions. Warehouse class codes are used when suggesting item placement in bins. You assign the warehouse class codes to product groups, which are then assigned to items and SKUs, or to zones and bins that can accommodate the storage conditions required by the warehouse class codes.  
  
 You are now ready to set up zones, if you want to operate zones in your warehouse. Using zones reduces the number of fields you need to fill in when you set up your bins, because bins created within zones inherit several properties from the zone. Zones can also make it easier for new or temporary employees to orient themselves in your warehouse. Note that flow is controlled by bins, therefore it is possible to operate with bins and only one zone.  
  
### To set up a zone in your warehouse  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Select the location where you want to set up zone and open the location card.  
  
3.  On the **Navigate** tab, in the **Location** group, choose **Zones**.  
  
4.  In the **Zones** window, fill in the **Code** and **Description** fields for each zone you want to operate.  
  
5.  If appropriate, in the **Bin Type** field, select the bin type that you want to apply to the bins within the zone.  
  
6.  If appropriate, in the **Warehouse Class Code** field, select a warehouse class code.  
  
7.  Select a special equipment code in the **Special Equipment Code** field if you want your employees to use a particular piece of equipment while working in the zone.  
  
8.  Fill in the **Zone Ranking** field with the ranking that you want for most of the bins in the zone.  
  
 When you change a zone parameter, all bins created thereafter in that zone will have the new characteristics, but the original bins will not be changed.  
  
> [!NOTE]  
>  If you want to operate without zones, you must still create one zone code that is undefined except for the code.  
  
 The next step in setting up the warehouse is to define bins. For more information, see [How to: Set Up Locations to Use Bins](../WarehouseActivities/how-to-set-up-locations-to-use-bins.md).  
  
 In addition, you must create put\-away templates and counting periods. For more information, see [How to: Set Up Put\-away Templates](../WarehouseActivities/how-to-set-up-put-away-templates.md) and [How to: Set Up Physical Inventory Counting Periods](../WarehouseActivities/how-to-set-up-physical-inventory-counting-periods.md).  
  
## See Also  
 [Configure Warehouse Processes](../WarehouseActivities/configure-warehouse-processes.md)   
 [How to: Set Up Items for Directed Put\-away and Pick](../WarehouseActivities/how-to-set-up-items-for-directed-put-away-and-pick.md)   
 [How to: Convert Existing Locations to Warehouse Locations](../WarehouseActivities/how-to-convert-existing-locations-to-warehouse-locations.md)   
 [About Warehouse Management](../WarehouseActivities/about-warehouse-management.md)   
 [Design Details: Warehouse Management](../ApplicationDesign/design-details-warehouse-management.md)