---
    title: How to Calculate Production Order Components | Microsoft Docs
    description: If you have amended production order lines, you must also refresh the components of the production order.
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
# How to: Calculate Production Order Components
If you have amended production order lines, you must also refresh the components of the production order.  
  
 In the following procedure, the components are calculated for a firm planned production order. This can also be done for production orders with a different status.  
  
### To calculate production order components  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Firm Planned Prod. Order**, and then choose the related link.  
  
2.  Open the relevant firm planned prod. order  from the list.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh**. The **Refresh Production Order** window opens.  
  
     On the **Production Order** FastTab, the current production order has been selected as a default.  
  
4.  The following table describes the options available for this batch job.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------|---------------------------------------|  
    |**Scheduling Direction**|**Forward**|This field has no effect on the outcome.|  
    ||**Backward**|This field has no effect on the outcome.|  
    |**Calculate**|**Lines**|You must leave the field blank to retain the current production order line.|  
    ||**Routings**|This field has no effect on the outcome.|  
    ||**Component Need**|Select this field to calculate component need.|  
    |**Warehouse**|**Create Inbound Request**|This field has no effect on the outcome.|  
  
5.  Choose the **OK** button to confirm your selections. The production order components are refreshed.  
  
> [!NOTE]  
>  Calculating production order components deletes previous changes in the components.  
  
## See Also  
 [How to: Refresh Production Orders](../how-to-refresh-production-orders.md)   
 [How to: Calculate Lines from Production Order Headers](../how-to-calculate-lines-from-production-order-headers.md)   
 [How to: Calculate Production Order Routing Lines](../how-to-calculate-production-order-routing-lines.md)   
 [How to: Use the Manufacturing Batch Unit of Measure](../how-to-use-the-manufacturing-batch-unit-of-measure.md)