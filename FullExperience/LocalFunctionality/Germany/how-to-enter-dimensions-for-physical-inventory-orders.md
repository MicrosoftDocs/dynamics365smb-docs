---
title: "How to: Enter Dimensions for Physical Inventory Orders"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, dimensions"
ms.assetid: 42e12fd6-1e02-4a49-96c8-14615235e41a
caps.latest.revision: 7
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Enter Dimensions for Physical Inventory Orders
After you have created a physical inventory order, you can enter dimensions for this order.  
  
 The application distinguishes between the dimensions for the physical inventory order header and the dimensions for the physical inventory order lines. The dimensions of the physical inventory header are a pattern for the dimensions of the physical inventory order lines. Every time you create a new physical inventory order line manually or automatically, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] will transfer the dimensions from the header to the new line.  
  
 That is why you should create the physical inventory order lines first after complete entering the dimensions for the physical inventory order header. You can manually change the dimensions for every physical inventory order line. For posting, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] will use the dimensions of the physical inventory order line.  
  
### To enter dimensions for a physical inventory order  
  
1.  In the **Search** box, enter **Phys. Inventory Order**, and then choose the related link.  
  
2.  Select the physical inventory order that you want to create an inventory recording for, and then, on the **Home** tab, choose **Edit**.  
  
3.  On the **Navigate** tab, choose **Dimensions**.  
  
4.  In the **Edit Dimension Set Entries** window, enter the dimensions for the inventory order header.  
  
     For more information, see [Edit Dimension Set Entries](assetId:///0f6ebbd8-9d92-4912-8637-6e9eda920381).  
  
5.  Create a new physical inventory order line and enter the item number.  
  
6.  Choose **Line**, and then choose **Dimensions**.  
  
7.  In the **Edit Dimension Set Entries** window, optionally, enter the dimensions for the inventory order line.  
  
## See Also  
 [How to: Enter Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-physical-inventory-orders.md)   
 [How to: Post Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-post-physical-inventory-orders.md)   
 [Phys. Invt. Order Diff. List](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-r_5005350-phys.-invt.-order-diff.-list-$-.md)   
 [Dimension Set Entries Overview](../../ApplicationDesign/dimension-set-entries-overview.md)