---
    title: Create Production Orders from Sales Orders
    description: Learn the different ways to create production orders for produced items directly from sales orders.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 99000883, 99000884
    ms.date: 06/22/2021
    ms.author: edupont

---
# Create Production Orders from Sales Orders
You can create production orders for produced items directly from sales orders.  

## To create a production order from a sales order  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Select the sales order you want to create a production order for.  
3.  Choose the **Planning** action. On the **Sales Order Planning** page, you can view the availability of the sales order item.  
4.  Choose the **Create Prod. Order** action.  
5.  Select the status and order type.  
6.  Choose the **Yes** button to create one or more production orders for the lines that have **Prod. Order** in their **Replenishment System** field.


> [!NOTE]  
> Demand lines in the created production order that have **Prod. Order** in their **Replenishment System** field represent underlying production orders. After you have generated these production orders, remember to identify any unfulfilled component demand for them using the **Order Planning** page or the **Replan** function from created orders. 

## Order type  
You can choose between two ways to create the production orders as outlined in the following table.

|Option|Description|
|------|-----------|
|Item Order|One production order is created for each needed production order that is represented by a line in the **Sales Order Planning** window.|
|Project Order|One production order is created for all needed production orders order that are represented by lines in the **Sales Order Planning** window. |

When you use project orders, the **Source Type** field of the production order contains **Sales Header** and the order has multiple lines, one for each sales line item that must be produced.  


## See Also  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
