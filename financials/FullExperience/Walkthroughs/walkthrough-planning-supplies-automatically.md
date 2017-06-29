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
# Walkthrough: Picking and Shipping in Basic Warehousing
In ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->, the outbound processes for picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.  
  
|Method|Inbound process|Bins|Picks|Shipments|Complexity level \(See [Design Details: Warehouse Setup](../ApplicationDesign/design-details-warehouse-setup.md)\)|  
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post pick and shipment from the order line|X|||2|  
|B|Post pick and shipment from an inventory pick document||X||3|  
|C|Post pick and shipment from a warehouse shipment document|||X|4\/5\/6|  
|D|Post pick from a warehouse pick document and post shipment from a warehouse shipment document||X|X|4\/5\/6|  
  
 For more information, see [Design Details: Outbound Warehouse Flow](../ApplicationDesign/design-details-outbound-warehouse-flow.md).  
  
 The following walkthrough demonstrates method B in the previous table.  
  
## About This Walkthrough  
 In basic warehousing where your location is set up to require pick processing but not ship processing, you use the **Inventory Pick** window to record and post pick and ship information for your outbound source documents. The outbound source document can be a sales order, purchase return order, outbound transfer order, or a production order with component need.  
  
 This walkthrough demonstrates the following tasks:  
  
-   Setting up SILVER location for inventory picks.  
  
-   Creating a sales order for customer 10000 for 30 loudspeakers.  
  
-   Releasing the sales order for warehouse handling.  
  
-   Creating an inventory pick based on a released source document.  
  
-   Registering the warehouse movement from the warehouse and at the same time posting the sales shipment for the source sales order.  
  
## Roles  
 This walkthrough demonstrates tasks that are performed by the following user roles:  
  
-   Warehouse Manager  
  
-   Order Processor  
  
-   Warehouse Worker  
  
## Prerequisites  
 To complete this walkthrough, you will need:  
  
-   ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> with the ADD INCLUDE<!--[!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)]--> installed.  
  
-   To make yourself a warehouse employee at SILVER location by following these steps:  
  
    1.  In the **Search** box, enter **Warehouse Employees**, and then choose the related link.  
  
    2.  Choose the **User ID** field, and select your own user account in the **Users** window.  
  
    3.  In the **Location Code** field, enter SILVER.  
  
    4.  Select the **Default** field.  
  
-   Make item LS-81 available at SILVER location by following these steps:  
  
    1.  In the **Search** box, enter **Item Journals**, and then choose the related link.  
  
    2.  Open the default journal, and then create two item journal lines with the following information about the work date \(January 23\).  
  
        |Entry Type|Item Number|Location Code|Bin Code|Quantity|  
        |----------------|-----------------|-------------------|--------------|--------------|  
        |Positive Adjmt.|LS-81|SILVER|S-01-0001 **Note:**  The item’s default bin in ADD INCLUDE<!--[!INCLUDE[demo](../ApplicationDesign/includes/demo_md.md)]-->.|20|  
        |Positive Adjmt.|LS-81|SILVER|S-01-0002|20|  
  
    3.  On the **Actions** tab, in the **Posting** group, choose **Post**, and then select the **Yes** button.  
  
## Story  
 Ellen, the warehouse manager at ADD INCLUDE<!--[!INCLUDE[demoname](../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/includes/demoname_md.md)]-->, sets up SILVER warehouse for basic pick handling where warehouse workers process outbound orders individually. Susan, the order processor, creates a sales order for 30 units of item LS-81 to be shipped to customer 10000 from the SILVER Warehouse. John, the warehouse worker must make sure that the shipment is prepared and delivered to the customer. John manages all involved tasks in the **Inventory Pick** window, which automatically points to the bins where LS-81 is stored.  
  
## Setting Up the Location  
 The setup of the **Location Card** window defines the company’s warehouse flows.  
  
### To set up the location  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Open the SILVER location card.  
  
3.  Select the **Require Pick** check box.  
  
## Creating the Sales Order  
 Sales orders are the most common type of outbound source document.  
  
### To create the sales order  
  
1.  In the **Search** box, enter **Sales Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Create a sales order for customer 10000 on the work date \(January 23\) with the following sales order line.  
  
    |Item|Location Code|Quantity|  
    |----------|-------------------|--------------|  
    |LS\_81|SILVER|30|  
  
     Proceed to notify the warehouse that the sales order is ready for warehouse handling.  
  
4.  On the **Actions** tab, in the **Release** group, choose **Release**.  
  
     John proceeds to pick and ship the sold items.  
  
## Picking and Shipping Items  
 In the **Inventory Pick** window, you can manage all outbound warehouse activities for a specific source document, such as a sales order.  
  
### To pick and ship items  
  
1.  In the **Search** box, enter **Inventory Picks**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Select the **Source Document** field, and then select **Sales Order**.  
  
4.  Select the **Source No.** field, select the line for the sale to customer 10000, and then choose the **OK** button.  
  
     Alternatively, on the **Actions** tab, in the **Functions** group, choose **Get Source Document**, and then select the sales order.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Autofill Qty. to Handle**.  
  
     Alternatively, in the **Qty. to Handle** field, enter 10 and 30 respectively on the two inventory pick lines.  
  
6.  On the **Actions** tab, in the **Posting** group, choose **Post**, select **Ship**, and then choose the **OK** button.  
  
     The 30 loudspeakers are now registered as picked from bins S-01-0001 and S-01-0002, and a negative item ledger entry is created reflecting the posted sales shipment.  
  
## See Also  
 Inventory Pick   
 Location Card   
 [How to: Pick Items with Inventory Picks](../DesignAndEngineering/how-to-pick-items-with-inventory-picks.md)   
 [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md)   
 [How to: Set Up Basic Warehouses with Operations Areas](../WarehouseActivities/how-to-set-up-basic-warehouses-with-operations-areas.md)   
 [How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Pick for Production in Basic Warehousing](../WarehouseActivities/how-to-pick-for-production-in-basic-warehousing.md)   
 [How to: Move Items Ad Hoc in Basic Warehousing](../WarehouseActivities/how-to-move-items-ad-hoc-in-basic-warehousing.md)   
 [Design Details: Outbound Warehouse Flow](../ApplicationDesign/design-details-outbound-warehouse-flow.md)   
 [Business Process Walkthroughs](../GettingStarted/business-process-walkthroughs.md)