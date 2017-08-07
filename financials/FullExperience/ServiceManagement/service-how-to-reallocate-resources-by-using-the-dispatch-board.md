---
    title: How to Reallocate Resources by Using the Dispatch Board | Microsoft Docs
    description: If the resource allocated to a service task cannot accomplish the work, it means that this service task needs reallocation. Usually you reallocate resources to a service task by using the **Dispatch Board**.
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
# How to: Reallocate Resources by Using the Dispatch Board
If the resource allocated to a service task cannot accomplish the work, it means that this service task needs reallocation. Usually you reallocate resources to a service task by using the **Dispatch Board**.  
  
### To reallocate a resource using the dispatch board  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dispatch Board**, and then choose the related link.  
  
2.  In the **Allocation Filter** field, select **Reallocation Needed**. The **Dispatch Board** window now shows the list of service orders that include service tasks that need reallocation.  
  
3.  Select the relevant service order. On the **Navigate** tab, in the **Planning** group, choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
4.  Select the allocation entry with the service task you want to reallocate a resource to.  
  
5.  In the **Resource No.** field, select the relevant resource. It overwrites the resource number already in the field.  
  
6.  Press Enter. The **Reallocation Entry Reasons** dialog box opens, asking whether you want to reallocate this entry. Fill in the **Reason Code** field if appropriate and choose the **Yes** button to confirm the reallocation.  
  
7.  Fill in the **Allocation Date** and **Allocated Hours** fields. The entry now contains the new resource and its status is **Active**.  
  
    > [!NOTE]  
    >  The old entry still exists but the status is updated in the following ways:  
    >   
    >  1.  If service was started while the allocation was **Active**, that is, if the repair status of the service item in the entry was changed to **In Process**, the allocation status changes from **Reallocation Needed** to **Finished**.  
    > 2.  If service was not started while the allocation was **Active**, the allocation status changes from **Reallocation Needed** to **Canceled**.  
    > 3.  If you are reallocating a service order that you have converted from a quote, the status of the allocation entries registered for the quote always changes to **Finished** when you reallocate the service items in the service order.  
  
8.  Repeat these steps for each service task you want to reallocate.  
  
## See Also  
 [Allocation Status and Repair Status](../allocation-status-and-repair-status.md)   
 [How to: Allocate Resources by Using Service Orders](../how-to-allocate-resources-by-using-service-orders.md)   
 [How to: Allocate Resources by Using the Dispatch Board](../how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Cancel Allocations](../how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using Service Orders](../how-to-reallocate-resources-by-using-service-orders.md)   
 [How to: Use the Dispatch Board](../how-to-use-the-dispatch-board.md)