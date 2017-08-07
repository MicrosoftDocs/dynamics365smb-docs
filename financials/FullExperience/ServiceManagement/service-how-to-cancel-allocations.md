---
    title: How to: Cancel Allocations | Microsoft Docs
    description: If you need to cancel allocations of resources, for example, technicians, to service tasks without reallocating the tasks directly, you can cancel the allocations.
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
# How to: Cancel Allocations
If you need to cancel allocations of resources, for example, technicians, to service tasks without reallocating the tasks directly, you can cancel the allocations.  
  
### To cancel an allocation  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dispatch Board**, and then choose the related link.  
  
2.  Browse to the relevant service order. On the **Navigate** tab, in the **Planning** group, choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
3.  Select the allocation entry with the service task that you want to cancel allocation for.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Cancel Allocation**.  
  
5.  A dialog box opens. In the **Reason Code** field, select the appropriate reason code.  
  
6.  Choose the **Yes** button to confirm the cancellation.  
  
     In the **Status** field, the **Reallocation Needed** option is automatically selected. If the repair status of the service item in the entry is **Initial**, the repair status is changed to **Referred**, that is, no service has been started. If the repair status is **In Process**, it is changed to **Partly Serviced**, that is, some service has been completed.  
  
 Repeat these steps for each service task that you want to cancel allocation for.  
  
## See Also  
 [How to: Reallocate Resources by Using the Dispatch Board](../how-to-reallocate-resources-by-using-the-dispatch-board.md)   
 [Allocation Status and Repair Status](../allocation-status-and-repair-status.md)