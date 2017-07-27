---
    title: Walkthrough: Receiving and Putting Away in Basic Warehousing | Microsoft Docs
    description: In ADD INCLUDE<!--[!INCLUDE[navnow](includes/navnow_md.md)]-->, the inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.
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
# Walkthrough: Receiving and Putting Away in Basic Warehousing
In ADD INCLUDE<!--[!INCLUDE[navnow](includes/navnow_md.md)]-->, the inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.  
  
|Method|Inbound process|Bins|Receipts|Put-aways|Complexity level (See [Design Details: Warehouse Setup](FullExperience/design-details-warehouse-setup.md))|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post receipt and put-away from the order line|X|||2|  
|B|Post receipt and put-away from an inventory put-away document|||X|3|  
|C|Post receipt and put-away from a warehouse receipt document||X||4/5/6|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document||X|X|4/5/6|  
  
 For more information, see [Design Details: Inbound Warehouse Flow](FullExperience/design-details-inbound-warehouse-flow.md).  
  
 The following walkthrough demonstrates method B in the previous table.  
  
## About This Walkthrough  
 In basic warehousing where your location is set up to require put-away processing but not receive processing, you use the **Inventory Put-away** window to record and post put-away and receipt information for your inbound source documents. The inbound source document can be a purchase order, sales return order, inbound transfer order, or production order with output that is ready to be put away.  
  
 This walkthrough demonstrates the following tasks.  
  
-   Setting up SILVER location for inventory put aways.  
  
-   Setting up SILVER location for bin handling.  
  
-   Defining a default bin for item LS-81. (LS-75 is already set up in ADD INCLUDE<!--[!INCLUDE[demo](includes/demo_md.md)]-->.)  
  
-   Creating a purchase order for vendor 10000 for 40 loudspeakers.  
  
-   Verifying that the put-away bins are preset by setup.  
  
-   Releasing the purchase order for warehouse handling.  
  
-   Creating an inventory put-away based on a released source document.  
  
-   Verifying that the put-away bins are inherited from the purchase order.  
  
-   Registering the warehouse movement into the warehouse and at the same time posting the purchase receipt for the source purchase order.  
  
## Roles  
 This walkthrough demonstrates tasks that are performed by the following user roles:  
  
-   Warehouse Manager  
  
-   Purchasing Agent  
  
-   Warehouse Worker  
  
## Prerequisites  
 To complete this walkthrough, you will need:  
  
-   ADD INCLUDE<!--[!INCLUDE[navnow](includes/demolong_md.md)]--> installed.  
  
-   To make yourself a warehouse employee at SILVER location by following these steps:  
  
    1.  In the **Search** box, enter **Warehouse Employees**, and then choose the related link.  
  
    2.  Choose the **User ID** field, and select your own user account in the **Users** window.  
  
    3.  In the **Location Code** field, enter SILVER.  
  
    4.  Select the **Default** field.  
  
## Story  
 Ellen, the warehouse manager at ADD INCLUDE<!--[!INCLUDE[demoname](includes/demo_md.md)]-->, creates a purchase order for 10 units of item LS-75 and 30 units of item LS-81 from vendor 10000 to be delivered to SILVER Warehouse. When the delivery arrives at the warehouse, John, the warehouse worker, puts the items away in default bins defined for the items. When John posts the put-away, the items are posted as received into inventory and available for sale or other demand.  
  
## Setting up the Location  
 The setup of the **Location Card** window defines the company’s warehouse flows.  
  
### To set up the location  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Open the SILVER location card.  
  
3.  Select the **Require Put-away** check box.  
  
     Proceed to set up a default bin for the two item numbers to control where they are put away.  
  
4.  On the **Navigate** tab, in the **Location** group, choose **Bins**.  
  
5.  Select the first row, for bin S-01-0001, and then on the **Home** tab, in the **Bins** group, choose **Contents**.  
  
     Notice in the **Bin Content** window that item LS-75 is already set up as content in bin S-01-0001.  
  
6.  On the **Home** tab, in the **New** group, choose **New**.  
  
7.  Select the **Fixed** and the **Default** fields.  
  
8.  In the **Item No.** field, enter LS-81.  
  
## Creating the Purchase Order  
 Purchase orders are the most common type of inbound source document.  
  
### To create the purchase order  
  
1.  In the **Search** box, enter **Purchase Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Create a purchase order for vendor 10000 on the work date (January 23) with the following purchase order lines.  
  
    |Item|Location code|Bin code|Quantity|  
    |----------|-------------------|--------------|--------------|  
    |LS_75|SILVER|S-01-0001|10|  
    |LS-81|SILVER|S-01-0001|30|  
  
    > [!NOTE]  
    >  The bin code is entered automatically according to the setup that you performed in the “Setting up the Location” section.  
  
     Proceed to notify the warehouse that the purchase order is ready for warehouse handling when the delivery arrives.  
  
4.  On the **Actions** tab, in the **Release** group, choose **Release**.  
  
     The delivery of loudspeakers from vendor 10000 has arrived at SILVER warehouse, and John proceeds to put them away.  
  
## Receiving and Putting the Items Away  
 In the **Inventory Put-away** window, you can manage all inbound warehouse activities for a specific source document, such as a purchase order.  
  
### To receive and put the items away  
  
1.  In the **Search** box, enter **Inventory Put-aways**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Select the **Source Document** field, and then select **Purchase Order**.  
  
4.  Select the **Source No.** field, select the line for the purchase from vendor 10000, and then choose the **OK** button.  
  
     Alternatively, on the **Actions** tab, in the **Functions** group, choose **Get Source Document**, and then select the purchase order.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Autofill Qty. to Handle**.  
  
     Alternatively, in the **Qty. to Handle** field, enter 10 and 30 respectively on the two inventory put-away lines.  
  
6.  On the **Actions** tab, in the **Posting** group, choose **Post**, select **Receive**, and then choose the **OK** button.  
  
     The 40 loudspeakers are now registered as put away in bin S-01-0001, and a positive item ledger entry is created reflecting the posted purchase receipt.  
  
## See Also  
 Inventory Put-away   
 Location Card   
 [How to: Put Items Away with Inventory Put-aways](FullExperience/how-to-put-items-away-with-inventory-put-aways.md)   
 [How to: Set Up Basic Warehouses with Operations Areas](FullExperience/how-to-set-up-basic-warehouses-with-operations-areas.md)   
 [How to: Move Components to an Operation Area in Basic Warehousing](FullExperience/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Pick for Production in Basic Warehousing](FullExperience/how-to-pick-for-production-in-basic-warehousing.md)   
 [How to: Move Items Ad Hoc in Basic Warehousing](FullExperience/how-to-move-items-ad-hoc-in-basic-warehousing.md)   
 [Design Details: Inbound Warehouse Flow](FullExperience/design-details-inbound-warehouse-flow.md)   
 [Business Process Walkthroughs](FullExperience/business-process-walkthroughs.md)