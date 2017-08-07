---
    title: How to Allocate Resources to All Service Items in a Service Order | Microsoft Docs
    description: You can allocate the same resource, for example, a technician, or resource group to all the service items in a service order by using the **Resource Allocations** window.
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
# How to: Allocate Resources to All Service Items in a Service Order
You can allocate the same resource, for example, a technician, or resource group to all the service items in a service order by using the **Resource Allocations** window.  
  
 Before you can allocate to all service items in the order, you need to allocate the resource or resource group to one service item in the order.  
  
### To allocate a resource to all service items in a service order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dispatch Board**, and choose the related link.  
  
2.  Browse to the relevant service order.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Resource Allocation**. The **Resource Allocations** window opens.  
  
4.  Select the allocation entry with the resource or resource group you have already allocated. The hours allocated in the **Allocated Hours** field will be divided between the allocation entries for all the service items in the order.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Allocate to All Service Items**.  
  
 Allocation entries are created for the other service items in the order with the same resource number and allocation date as the line you allocated. The allocated hours are the hours you allocated divided by the number of service items in the order. The **Status** field is automatically set to **Active** for all the entries that were created.  
  
## See Also  
 [How to: Allocate Resources by Using the Dispatch Board](../how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Allocate Resource Groups](../how-to-allocate-resource-groups.md)   
 [How to: Allocate Resources by Using Resource Availability](../how-to-allocate-resources-by-using-resource-availability.md)