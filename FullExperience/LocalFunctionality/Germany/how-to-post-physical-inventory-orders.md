---
title: "How to: Post Physical Inventory Orders"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, orders"
  - "physical inventory, posting"
  - "posting, physical inventory orders"
ms.assetid: 11f7c7fc-cb3e-4aa9-8275-3665c42821f5
caps.latest.revision: 32
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Post Physical Inventory Orders
After completing a physical inventory order and changing its status to **Finished**, you can post it.  
  
 You can set the status of a physical inventory order to **Finished** if the following is true:  
  
-   All related physical inventory recordings have a status of **Finished**.  
  
-   Each physical inventory order line has been counted by at least one inventory recording line.  
  
-   The **In Recording Lines** and the **Qty. Exp. Calculated** check boxes have been selected for all of the physical inventory order lines.  
  
 After posting the order, you can view the posted physical inventory orders. Posted inventory documents provide a complete overview of the physical inventory process.  
  
### To post a physical inventory order  
  
1.  In the **Search** box, enter **\($ N\_5005350 Phys. Inventory Order $\)**, and then choose the related link.  
  
2.  Select the physical inventory order that you want to complete, and then, on the **Home** tab, choose **Edit**.  
  
     In the **\($ N\_5005350 Phys. Inventory Order $\)** window, you can view the quantity recorded after taking physical inventory in the **Qty. Recorded \(Base\)** field.  
  
3.  On the **Home** tab, in the **Process** group, choose **Finish**.  
  
4.  Choose the **Yes** button. The value in the **Status** field is changed to **Finished**.  
  
    > [!NOTE]  
    >  You cannot change the physical inventory order header or the physical inventory order lines.  
  
5.  To post the order, choose **Post**, and then choose the **OK** button.  
  
### To view posted physical inventory orders  
  
1.  In the **Search** box, enter **\($ N\_5005358 Posted Phys. Invt. Order $\)**, and then choose the related link.  
  
2.  In the **\($ N\_5005358 Posted Phys. Invt. Order $\)** window, select the posted inventory order that you want to view, and then, on the **Home** tab, choose **View**.  
  
3.  To view a list of related physical inventory recordings, on the **Navigate** tab, in the **Order** group, choose **Recordings**.  
  
     You can also run a report that returns the difference between the expected quantity and the physical \(recorded\) quantity.  
  
4.  Close the window.  
  
## See Also  
 [Physical Inventory Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-documents.md)   
 [How to: Enter Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-physical-inventory-orders.md)