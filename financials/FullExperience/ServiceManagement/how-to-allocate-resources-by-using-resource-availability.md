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
# How to: Allocate Resources by Using Resource Availability
When you have created service orders or quotes, you can make use of resource availability to allocate resources, for example, technicians, to perform the service tasks in the orders or quotes.  
  
### To allocate a resource using resource availability  
  
1.  In the **Search** box, enter **Dispatch Board**, and choose the related link.  
  
2.  Browse to the relevant service order.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Resource Allocations**.  
  
4.  Select the entry with the service task to which you want to allocate a resource.  
  
5.  On the **Navigate** tab, in the **Planning** group, choose **Resource Availability**.  
  
6.  In the **Res. Availability \(Service\)** window, on the **Actions** tab, in the **General** group, choose **Show Matrix**.  
  
7.  Select a resource you want to allocate. You can base your selection on whether the resource is skilled for the task, whether it is located in the customer zone, and\/or whether it is preferred by the customer.  
  
8.  Select a date on which the resource has enough available hours for the task and which is close to the response date of the service order.  
  
9. In the **Quantity to Allocate** field, enter the number of hours you want to allocate the resource to the service task for.  
  
10. On the **Actions** tab, in the **Functions** group, choose **Allocate** to allocate the selected resource on the selected date.  
  
     The **Status** field is automatically set to **Active**.  
  
 Repeat these steps for each date that you want to allocate the resource to the service task.  
  
> [!NOTE]  
>  For a service item in a service order, there can only be **Active** allocation entries with one resource or resource group at a time.  
  
## See Also  
 [How to: Allocate Resources by Using the Dispatch Board](../FullExperience/how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Allocate Resources by Using Resource Group Availability](../FullExperience/how-to-allocate-resources-by-using-resource-group-availability.md)   
 [How to: Add Resource Capacity](../FullExperience/how-to-add-resource-capacity.md)   
 [How to: Assign Skill Codes to Resources](../FullExperience/how-to-assign-skill-codes-to-resources.md)   
 [How to: Assign Resources to Service Zones](../FullExperience/how-to-assign-resources-to-service-zones.md)