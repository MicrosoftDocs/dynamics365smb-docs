---
    title: How to: Calculate Production Order Routing Lines | Microsoft Docs
    description: If you have amended production order lines, you must also refresh the routing of the production order.
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
# How to: Calculate Production Order Routing Lines
If you have amended production order lines, you must also refresh the routing of the production order.  
  
 In the following procedure, the routing lines are calculated for a firm planned production order. This can also be done for production orders with a different status.  
  
### To calculate production order routing lines  
  
1.  In the **Search** box, enter **Firm Planned Prod. Order**, and then choose the related link.  
  
2.  Open the relevant firm planned production order  from the list.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh**. The **Refresh Production Order** window opens.  
  
4.  On the **Production Order** FastTab, the current production order has been selected as a default.  
  
5.  The following table describes the options available for this batch job.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------|---------------------------------------|  
    |**Scheduling Direction**|**Forward**|This field has no effect on the outcome.|  
    ||**Backward**|This field has no effect on the outcome.|  
    |**Calculate**|**Lines**|You must leave the field blank to retain the current production order line.|  
    ||**Routings**|Select this field to calculate routings.|  
    ||**Component Need**|This field has no effect on the outcome.|  
    |**Warehouse**|**Create Inbound Request**|This field has no effect on the outcome.|  
  
6.  Choose the **OK** button to confirm your selections. The production order routing lines are refreshed.  
  
> [!NOTE]  
>  Calculating production order routing lines deletes previous changes in the routings.  
  
## See Also  
 [How to: Refresh Production Orders](../how-to-refresh-production-orders.md)   
 [How to: Calculate Production Order Components](../how-to-calculate-production-order-components.md)   
 [How to: Calculate Lines from Production Order Headers](../how-to-calculate-lines-from-production-order-headers.md)