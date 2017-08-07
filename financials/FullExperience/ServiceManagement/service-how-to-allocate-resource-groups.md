---
    title: How to Allocate Resource Groups | Microsoft Docs
    description: When you have created service orders or quotes, you can allocate resource groups, for example, groups of technicians, to perform the service tasks in the orders or quotes.
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
# How to: Allocate Resource Groups
When you have created service orders or quotes, you can allocate resource groups, for example, groups of technicians, to perform the service tasks in the orders or quotes.  
  
### To allocate a resource group  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dispatch Board**, and choose the related link.  
  
2.  Browse to the relevant service order.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
4.  Select the nonactive allocation entry with the service task to which you want to allocate a resource.  
  
     If there is no nonactive allocation entry, you need to create one. On the **Home** tab, in the **New** group, choose **New**.  
  
5.  In the **Resource Group No.** field, choose the relevant resource group.  
  
     ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  
  
6.  Fill in the **Allocation Date** and **Allocated Hours** fields.  
  
     The status of the resource allocation is automatically updated to be **Active**.  
  
 Repeat these steps for each date that you want to allocate the resource group to the service task.  
  
> [!NOTE]  
>  For a service item in a service order, there can only be **Active** allocation entries with one resource or resource group at a time.  
  
## See Also  
 [How to: Allocate Resources by Using Resource Group Availability](../how-to-allocate-resources-by-using-resource-group-availability.md)   
 [How to: Allocate Resources by Using the Dispatch Board](../how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Cancel Allocations](../how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../how-to-reallocate-resources-by-using-the-dispatch-board.md)