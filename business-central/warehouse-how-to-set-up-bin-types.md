---
    title: How to Set Up Bin Types | Microsoft Docs
    description: You can direct the flow of items through bins that you have defined for particular warehouse activities. You give each bin its basic flow activities, and thereby define the way the way a bin is used, by assigning it a bin type.
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
# Set Up Bin Types
You can direct the flow of items through bins that you have defined for particular warehouse activities. You give each bin its basic flow activities, and thereby define the way the way a bin is used, by assigning it a bin type.  

There are six types. You can operate your warehouse with all of the six possible bin types, or you can choose to operate with just the RECEIVE, PUTPICK, SHIP and QC bin types. These four bin types enable suggestions to be made that support the flow of items and allow you to record inventory discrepancies.  

## To set up the bin types you want to use  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bin Types**, and then choose the related link.  
2.  On the **Bin Types** page, create a 10-character code for a bin type.  
3.  Select the activities that can be performed with each bin type.  

> [!NOTE]  
>  Bin types are only applicable if you are using directed put-away and pick for your location.  

The bin type determines only how a bin is used when processing the flow of items through the warehouse. You can always override the suggestions for any warehouse document, and you can move items in or out of any bin by performing a warehouse movement.  

The bin types that you can create are listed below.  

|Bin Type|Description|  
|------------------|---------------------------------------|  
|RECEIVE|Items registered as posted receipts but not yet put away.|  
|SHIP|Items picked for warehouse shipment lines but not yet posted as shipped.|  
|PUT AWAY|Typically, items to be stored in large units of measure but that you do not want to access for picking purposes. Because these bins are not used for picking, either for production orders or shipments, your use of a Put Away type bin might be limited, but this bin type could be useful if you have purchased a large quantity of items. Bins of this type should always have a low bin-ranking, so that when received items are put away, other higher-ranking PUTPICK bins fixed to the item are put away first. If you are using this type of bin, you must regularly perform bin replenishment so that the items stored in these bins are also available in PUTPICK or PICK type bins.|  
|PICK|Items to be used only for picking, for example, for items with an approaching expiration date that you have moved into this type of bin. You would place a high bin ranking on these bins so they are suggested for picking first.|  
|PUTPICK|Items in bins that are suggested for both the put-away and pick functions. Bins of this type probably have different bin rankings. You can set up your bulk storage bins as this type of bin with low bin rankings compared to your ordinary pick bins or forward picking area bins.|  
|QC|This bin is used for inventory adjustments if you specify this bin on the location card in the **Adjustment Bin Code** field. You can also set up bins of this type for defective items and items being inspected. You can move items to this type of bin if you want to make them inaccessible to the usual item flow.<br /><br /> **NOTE:** Unlike all other bin types, the **QC** bin type has none of the item handling check boxes selected by default. This indicates that any content you place in a QC bin is excluded from item flows.|  

## See Also
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
