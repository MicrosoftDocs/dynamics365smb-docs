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
# Example - Different Machine Centers Assigned  to a Work Center
It is important to plan which capacities are to make up the total capacity when setting up the machine centers and work centers.  
  
 If different machine centers \(such as 210 Packing table 1, 310 Painting Cabin ...\) are assigned to a work center, the consideration of the single capacities of the machine centers is significant because failure of one machine center can interrupt the entire process. The machine groups can be entered according to their capacity but may not be included in the planning. By deactivating the **Consolidated Calendar** field only the capacity of the work center but not the machine center is assigned in the planning.  
  
 If, however, identical machine centers \(such as 210 Packing table 1 and 220 Packing table 2\) are combined in a work center, the consideration of the work center as a sum of the assigned machine centers is of interest. Therefore, the work center would be listed with zero capacity. By activating the **Consolidated Calendar** field, the common capacity is assigned to the work center.  
  
 If capacities of work centers are to make no contribution to the total capacity, you can achieve this with efficiency \= 0.  
  
## See Also  
 Work Center Card   
 Machine Center Card   
 [Shop Calendars](../OperationsPlanning/shop-calendars.md)   
 Consolidated Calendar