---
    title: How to Refresh Production Orders | Microsoft Docs
    description: This planning function calculates changes made to a production order header and does not involve production BOM levels.
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
# How to: Refresh Production Orders
This planning function calculates changes made to a production order header and does not involve production BOM levels.  
  
 The **Refresh** function calculates and initiates the values of the component lines and routing lines based on the master data defined in the assigned production BOM and routing, according to the order quantity and due date on the production order’s header. It is typically used after you have done one of the following:  
  
-   Created a production order header manually to calculate and create line data for the first time.  
  
-   Made changes to the production order header to recalculate all the line data.  
  
> [!NOTE]  
>  You can change component lines and routing lines, and the production order schedule is updated accordingly. When you refresh, those changes are cancelled as the order is reset according to master data.  
  
### To refresh a production order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Planned Production Orders**, and then choose the related link.  
  
2.  Create a new production order or open one that you want to refresh and change the **Quantity** or **Due Date** fields.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh Production Order**.  
  
     In the **Refresh Production Order** window, on the **Options** FastTab, define how and what to refresh.  
  
4.  In the **Scheduling Direction** field, select one of the following options.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Back**|To calculate the operation sequence backwards from the earliest possible ending date, as defined by due date and other scheduled orders, to the latest possible starting date.<br /><br /> **NOTE:** This default option is relevant in the majority of situations.|  
    |**Forward**|To calculate the operation sequence forward from the latest possible starting date, as defined by due date and other scheduled orders, to the earliest possible ending date.<br /><br /> **NOTE:** This option is relevant for ASAP orders.|  
  
5.  In the **Calculate** field, select which parts of the production order to calculate when refreshing.  
  
6.  Select the **Warehouse – Create Inbound Request** field to create a warehouse request for the putting away of the production order's components.  
  
    > [!NOTE]  
    >  The warehouse location must be set up to require put-away processing but not directed put-away and pick.  
  
7.  Choose the **OK** button to start the **Refresh** function according to your settings.  
  
> [!NOTE]  
>  You cannot refresh a reserved production order. You can restore the reservation after the production order is refreshed, but in that case you should cancel the reservation before you refresh.  
  
> [!NOTE]  
>  Changes implemented with the **Refresh** function are very likely to change the capacity need of the production order. You may have to reschedule operations afterwards.  
  
## See Also  
 [How to: Replan Production Orders](../how-to-replan-production-orders.md)   
 [About Production Orders](../about-production-orders.md)