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
# How to: Reallocate Resources by Using Service Orders
You can reallocate resources directly from a service order or service quote when you are working with it.  
  
### To reallocate resources using a service order  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  Select the service item line corresponding to the service task you want to allocate a resource to.  Choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
4.  In the **Resource Allocations** window, select an allocation entry with the service task you want to reallocate the resource to. In the **Resource No.** field, select the relevant resource. This overwrites the resource number already in the field.  
  
5.  Press the Enter key. A dialog box opens, asking whether you want to reallocate this entry. Fill in the **Reason Code** field if appropriate and choose the **Yes** button to confirm the reallocation.  
  
6.  Fill in the **Allocation Date** and **Allocated Hours** fields. The entry now contains the new resource and its status is **Active**.  
  
    > [!NOTE]  
    >  The old entry still exists but its status is updated as follows:  
    >   
    >  -   If service was started while the allocation was **Active**, that is, if the repair status of the service item in the entry was changed to **In Process**, the allocation status changes from **Reallocation Needed** to **Finished**.  
    > -   If service was not started while the allocation was **Active**, allocation status changes from **Reallocation Needed** to **Canceled**.  
    > -   If you are reallocating a service order that you have converted from a quote, the status of the allocation entries registered for the quote always changes to **Finished** when you reallocate the service items in the service order.  
  
7.  Repeat these steps for each service task you want to reallocate.  
  
## See Also  
 [Allocation Status and Repair Status](../FullExperience/allocation-status-and-repair-status.md)   
 [How to: Allocate Resources by Using Service Orders](../FullExperience/how-to-allocate-resources-by-using-service-orders.md)   
 [How to: Allocate Resources by Using the Dispatch Board](../FullExperience/how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Cancel Allocations](../FullExperience/how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../FullExperience/how-to-reallocate-resources-by-using-the-dispatch-board.md)