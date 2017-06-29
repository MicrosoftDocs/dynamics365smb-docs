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
# How to: Allocate Resources by Using the Dispatch Board
When you have created and fulfilled a number of service orders and service quotes, you can use the **Dispatch Board** window to allocate resources, for example, technicians, to perform service tasks registered as service item lines in the documents.  
  
### To allocate a resource using the dispatch board  
  
1.  In the **Search** box, enter **Dispatch Board**, and then choose the related link.  
  
2.  Apply filters to view the documents that meet certain conditions. For more information about entering criteria in filters, see [Enter Criteria in Filters](../WorkingWithDynamics/enter-criteria-in-filters.md).  
  
3.  Select the document that contains the service task you want to allocate a resource to. On the **Navigation** tab, in the **Planning** group, choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
4.  In the **Resource Allocations** window, select a nonactive allocation entry with the service task you want to allocate the resource to. If the nonactive allocation entry doesn't exist, you can create a new one.  
  
5.  To create a new nonactive allocation entry, on the **Home** tab, in the **New** group, choose **New**, and specify the service task by filling in the **Service Item No.** field on the same line.  
  
6.  In the **Resource No.** field, select the relevant resource. If the resource is a member of a resource group, the number of the resource group is automatically entered into the **Resource Group No.** field.  
  
7.  Fill in the **Allocation Date** and **Allocated Hours** fields. The **Status** field is automatically set to **Active**. This means that the resource is allocated to the service task.  
  
> [!NOTE]  
>  For a service item in a service order, there can be only **Active** allocation entries with one resource or resource group at a time.  
  
## See Also  
 [How to: Allocate Resources by Using Service Orders](../Service/how-to-allocate-resources-by-using-service-orders.md)   
 [How to: Allocate Resources by Using Resource Availability](../Service/how-to-allocate-resources-by-using-resource-availability.md)   
 [How to: Allocate Resource Groups](../Service/how-to-allocate-resource-groups.md)   
 [How to: Cancel Allocations](../Service/how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../Service/how-to-reallocate-resources-by-using-the-dispatch-board.md)   
 [How to: Use the Dispatch Board](../Service/how-to-use-the-dispatch-board.md)