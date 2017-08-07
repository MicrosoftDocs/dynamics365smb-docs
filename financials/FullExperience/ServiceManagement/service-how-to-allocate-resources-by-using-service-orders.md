---
    title: How to: Allocate Resources by Using Service Orders | Microsoft Docs
    description: After you have created and filled in a service order or service quote, you can allocate resources, for example, technicians, to perform service tasks registered as service item lines in the document.
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
# How to: Allocate Resources by Using Service Orders
After you have created and filled in a service order or service quote, you can allocate resources, for example, technicians, to perform service tasks registered as service item lines in the document.  
  
### To allocate a resource using a service order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
  
2.  Select the relevant service order, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  Select the service item line corresponding to the service task you want to allocate a resource to.  
  
4.  On the **Lines** toolbar, on the **Line** menu, choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
5.  In the **Resource Allocations** window, select a nonactive allocation entry with the service task you want to allocate the resource to. If the nonactive allocation entry does not exist, you can create a new one.  
  
6.  To create a new nonactive allocation entry, on the **Actions** tab, choose **New**.  
  
7.  Specify the service task by filling in the **Service Item No.** field on the same line.  
  
8.  In the **Resource No.** field, select the relevant resource. If the resource is a member of a resource group, the number of the resource group is entered automatically into the **Resource Group No.** field.  
  
9. Fill in the **Allocation Date** and **Allocated Hours** fields. The **Status** field is set to **Active**. This means that the resource is allocated to the service task.  
  
> [!NOTE]  
>  For a service item in a service order, there can only be Active allocation entries with one resource or resource group at a time.  
  
## See Also  
 [Allocation Status and Repair Status](../allocation-status-and-repair-status.md)   
 [How to: Allocate Resources by Using the Dispatch Board](../how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Allocate Resources by Using Resource Availability](../how-to-allocate-resources-by-using-resource-availability.md)   
 [How to: Cancel Allocations](../how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../how-to-reallocate-resources-by-using-the-dispatch-board.md)