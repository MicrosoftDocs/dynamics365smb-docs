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
# How to: Refresh Planning Demands
You can use the **Refresh Planning Demand** batch job to refresh the planning components and the routing lines for the current planning line.  
  
### To refresh planning demands  
  
1.  In the **Search** box, enter **Planning Worksheet**, and then choose the related link.  
  
2.  In the **Planning Worksheet** window, select the line you want to refresh.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh Planning Line**.  
  
4.  On the **Requisition Line** FastTab, the filters are prepared for the current **Lot No.** field.  
  
5.  On the **Options** FastTab, you can make the following selections:  
  
    |Options|Selection|Description|  
    |-------------|---------------|-----------------|  
    |**Scheduling Direction**|**Forward**<br /><br /> **Back**|Scheduling starts from the starting date and proceeds forward to the finishing date.<br /><br /> Scheduling starts from the ending date and proceeds backward to the required starting date.|  
    |**Calculate**|**Routings**<br /><br /> **Component Need**|Select the field to refresh the planning routings.<br /><br /> Select the field to refresh the planning components.|  
  
6.  Choose the **OK** button to confirm your selections.  
  
## See Also  
 [How to: Plan for New Demand](../OperationsPlanning/how-to-plan-for-new-demand.md)   
 [How to: Replan Production Orders](../OperationsPlanning/how-to-replan-production-orders.md)   
 [How to: Run MPS and MRP](../OperationsPlanning/how-to-run-mps-and-mrp.md)