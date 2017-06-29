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
# How to: Enter Dimensions for Physical Inventory Orders
After you have created a physical inventory order, you can enter dimensions for this order.  
  
 The application distinguishes between the dimensions for the physical inventory order header and the dimensions for the physical inventory order lines. The dimensions of the physical inventory header are a pattern for the dimensions of the physical inventory order lines. Every time you create a new physical inventory order line manually or automatically, FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> --> will transfer the dimensions from the header to the new line.  
  
 That is why you should create the physical inventory order lines first after complete entering the dimensions for the physical inventory order header. You can manually change the dimensions for every physical inventory order line. For posting, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] will use the dimensions of the physical inventory order line.  
  
### To enter dimensions for a physical inventory order  
  
1.  In the **Search** box, enter **Phys. Inventory Order**, and then choose the related link.  
  
2.  Select the physical inventory order that you want to create an inventory recording for, and then, on the **Home** tab, choose **Edit**.  
  
3.  On the **Navigate** tab, choose **Dimensions**.  
  
4.  In the **Edit Dimension Set Entries** window, enter the dimensions for the inventory order header.  
  
     For more information, see Edit Dimension Set Entries.  
  
5.  Create a new physical inventory order line and enter the item number.  
  
6.  Choose **Line**, and then choose **Dimensions**.  
  
7.  In the **Edit Dimension Set Entries** window, optionally, enter the dimensions for the inventory order line.  
  
## See Also  
 [How to: Enter Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-physical-inventory-orders.md)   
 [How to: Post Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-post-physical-inventory-orders.md)   
 Phys. Invt. Order Diff. List   
 [Dimension Set Entries Overview](../../ApplicationDesign/dimension-set-entries-overview.md)