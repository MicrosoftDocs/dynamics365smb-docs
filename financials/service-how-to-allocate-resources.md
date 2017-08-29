---
    title: How to Allocate Resources | Microsoft Docs
    description: You can change the annual amount of the service contract or contract quote to correct the amount that will be invoiced annually.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: bholtorf

---

# How to: Allocate Resources
The key element to service management is the people who supply service. You can set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to assign the appropriate people to the appropriate jobs. Assignments can be based on service zones where the people are located or where the service occurs. In addition, you can group resources together when responding to service requests. For more information, see [How to: Set Up Resource Allocation](service-how-setup-resource-allocation.md).

You can allocate resources, for example, technicians, by using the **Dispatch Board**, or from a service order. You can use resource availability to allocate resources to perform the service tasks in the orders or quotes.

You can allocate the same resource, for example, a technician, or resource group to all the service items in a service order. Allocation entries are created for the other service items in the order with the same resource number and allocation date as the line you allocated. The allocated hours are the hours you allocated divided by the number of service items in the order. The **Status** field is automatically set to **Active** for all the entries that were created.

## To allocate a resource using resource or resource group availability    
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dispatch Board**, and choose the related link.  
2. Choose the service order, and then choose the **Resource Allocations** action.  
3. Choose the entry with the service task to which you want to allocate a resource.  
4. Choose either the **Resource Availability** or **Res. Group Availability** action.  
5. In the **Res. Availability (Service)** window, choose **Show Matrix**.  
6. Choose a resource to allocate. You can base your selection on whether the resource is skilled for the task, whether it is located in the customer zone, and/or whether it is preferred by the customer.  
7. Specify a date on which the resource has enough available hours for the task, and which is close to the response date of the service order.  
8. In the **Qty. to Allocate** field, enter the number of hours you want to allocate the resource to the service task for.  
9. On the **Actions** tab, in the **Functions** group, choose **Allocate** to allocate the selected resource on the selected date.  
  
     The **Status** field is automatically set to **Active**.  
  
 Repeat these steps for each date that you want to allocate the resource to the service task.  
  
> [!NOTE]  
>  For a service item in a service order, there can only be **Active** allocation entries with one resource or resource group at a time.  

## To allocate a resource using a service order  
After you have created and filled in a service order or service quote, you can allocate resources, for example, technicians, to perform service tasks registered as service item lines in the document.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Choose the service order, and then choose **Edit**.  
3. Choose the service item line corresponding to the service task you want to allocate a resource to.  
4. Choose **Resource Allocations**. 
5. In the **Resource Allocations** window, choose a nonactive allocation entry with the service task you want to allocate the resource to. If the allocation entry does not exist, you can create a new one by choosing **New**.  
7. Specify the service task by filling in the **Service Item No.** field on the same line.  
8. In the **Resource No.** field, choose the resource. If the resource is a member of a resource group, the number of the resource group is entered automatically into the **Resource Group No.** field.  
9. Fill in the **Allocation Date** and **Allocated Hours** fields. The **Status** field is set to **Active**. This means that the resource is allocated to the service task.  
10. Optionally, to assign the resource to all items, choose **Allocate to All Service Items**.
  
> [!NOTE]  
>  For a service item in a service order, there can only be active allocation entries with one resource or resource group at a time. 

## See Also
[How to: Set Up Resource Allocation](service-how-setup-resource-allocation.md)
[Allocation Status and Repair Status](service-allocation-status-and-repair-status.md)   