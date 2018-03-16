---
    title: How to Plan Project Orders | Microsoft Docs
    description: This planning task starts from a sales order and uses the **Sales Order Planning** window. Once you have created a project production order, you can plan it further by using the **Order Planning** window.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/06/2017
    ms.author: sgroespe

---
# Plan Project Orders
This planning task starts from a sales order and uses the **Sales Order Planning** window. Once you have created a project production order, you can plan it further by using the **Order Planning** window.  

## To create a project production order  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.  
2.  Select the sales order that represents the production project, and then choose the **Planning** action.  
4.  In the **Sales Order Planning** window, choose  the **Create Prod. Order** action.  
5.  In the **Create Order from Sales** window, in the **Order Type** field, select **Project Order**.  
6.  Choose the **Yes** button.  
7.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Production Orders**, and then choose the related link.
8. Open the production order just created.  

    Notice that the **Source Type** field of the production order contains **Sales Header** and the order has multiple lines, one for each sales line item that must be produced.  
9. Choose the **Planning** action.
10. In the **Order Planning** window, choose the **Refresh** action to calculate new demand.  

The order header line for the project order is displayed with all unfulfilled demand lines expanded under it. Although the production order contains lines for several produced items, the total demand for all production order lines is listed under one order header line in the **Order Planning** window, and the original customer name is displayed. You can now proceed to plan for the demand as described in [Plan for New Demand Order by Order](production-how-to-plan-for-new-demand.md).  

> [!NOTE]  
>  Demand lines in the project production order that have **Prod. Order** in their **Replenishment System** field represent underlying production orders. After you have generated these production orders, you must again calculate a plan in the **Order Planning** window to identify any unfulfilled component demand for them. In that case, they are displayed as demand lines under a normal production order header line, meaning, the project relation is no longer visible in the window. However, if you are using the Order Tracking feature, then you can look back and forth to all supply orders made under the original sales order.  

## See Also
[Planning](production-planning.md)   
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
