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
# Service Item Trendscape
The **Service Item Trendscape** window provides a scrollable summary of service ledger entries that are related to a specific service item. This summary is generated for a specific time period.  
  
 To use the trendscape, from the **Service Items** window, select a service item. On the **Navigate** tab, in the **Serv. Item** group, point to **Statistics**, and then choose **Trendscape**.  
  
 When you scroll up and down, the amounts \(in LCY\) are calculated according to the time interval that you have selected.  
  
 You can specify which service items are included in the trendscape by setting a filter in the **Service Item No**. field on the **General** FastTab.  
  
 The **Period Start** and **Period Name** fields on the **Lines** FastTab contain a series of dates that are determined by the time interval that you have selected in the **View by** field on the **Options** FastTab. Accounting periods are set up in the **Accounting Period** table.  
  
 The following table describes the other fields in the **Lines** FastTab.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Prepaid Income**|The total income \(in LCY\) that has been posted to the prepaid account with regard to the service item in the periods specified in the **Period Start** field.|  
|**Posted Income**|The total income \(in LCY\) that has been posted to the general ledger for the service item in the periods specified in the **Period Start** field.|  
|**Parts Used**|The cost of spare parts used in the period shown in the **Period Start** field.|  
|**Resources Used**|The cost of resources used in the specified period.|  
|**Cost Used**|The cost used in the specified period.|  
|**Profit**|The profit \(posted income minus posted cost in LCY\) for the service item in the period specified in the **Period Start** field.|  
|**Profit %**|The profit percentage for the service item in the specified period.|  
  
 All amounts are calculated from service ledger entries, which are entries that are created when you post service orders or service invoices.  
  
> [!IMPORTANT]  
>  If you have set the time interval to **Day** and you want to scroll over a long period, you can do it faster by shifting to a larger interval such as **Quarter**. When you have found the desired period, you can shift back to the original interval to see the data in more detail.  
  
## See Also  
 Service Item Trendscape