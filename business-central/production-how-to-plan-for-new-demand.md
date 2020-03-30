---
    title: How to Plan Order by Order | Microsoft Docs
    description: This planning task can be performed on the **Order Planning** page, which displays all new demand along with availability information and suggestions for supply. It provides the visibility and tools needed to effectively plan demand from sales lines and component lines and then create different types of supply orders directly.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Plan for New Demand Order by Order
This planning task can be performed on the **Order Planning** page, which displays all new demand along with availability information and suggestions for supply. It provides the visibility and tools needed to effectively plan demand from sales lines and component lines and then create different types of supply orders directly.  

You can enter the **Order Planning** page in two ways depending on your focus: From an order that you want to plan for specifically or in batch mode because you want to plan for all and any new demand.  


## To plan for new production order demand  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planned Production Orders**, and then choose the related link. (You can perform these steps for planned, firm planned, or released production orders).
2.  Open the production order you want to plan for, and then choose the **Planning** action.  
3.  On the **Order Planning** page, choose the **Calculate Plan** action.  

The page displays planning lines according to the view filter **Production Demand**, meaning unfulfilled component lines of all existing production orders. Demand for only the one production order is not shown because it is necessary to plan for one production order with an overview of demand for potentially earlier components lines. Planning lines for the production order in context are expanded.  

## To plan for any new demand  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Order Planning**, and then choose the related link.  
2.  On the **Order Planning** page, choose the **Calculate Plan** action.
3.  Choose the **Expand (+)** button in front of the date in the **Demand Date** field to see the underlying planning lines that represent demand lines with insufficient availability.  
4.  For each expanded planning line, that is, demand line, you can see values in information fields at the bottom of the page.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Qty. on Other Locations**|Shows if the item exists on another location. You can then look up and select it.|  
    |**Substitutes Exist**|Shows if a substitute item is created for the item. You can then look up and select it. Note that this feature only applies to components, that is, from demand lines of type **Production**.|  
    |**Quantity Available**|Shows the total availability of the item, that is, the Projected Available Balance.|  
    |**Earliest Date Available**|Shows the arrival date of an inbound supply order that can cover the needed quantity on a date later than the demand date.|  

5.  In the **Replenishment System** field, select which type of supply order to create.  

    The default value is that of the item card, or SKU card, but you can change it to one of three options:  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Purchase**|Creates a purchase order.|  
    |**Transfer**|Creates a transfer order.|  
    |**Prod. Order**|Creates a production order.|  

    In the **Supply From** field you must select a value according to the selected replenishment system.  

    > [!NOTE]  
    >  If the field is not filled in, the system will display an error message when you use the **Make Supply Order** function, and no supply order will be created for the planning line in question. This, however, is not the case if the replenishment system is **Prod. Order**.  

6.  From the **Supply From** field, you can look up in the relevant list and select where the supply should come from:  

    - If replenishment system is **Purchase**, the look-up button in this field looks up on the **Item Vendor Catalog** page.  
    - If replenishment system is **Transfer**, the look-up button in this field looks up on the **Location List** page.  

    In case the item exists in another location, the **Qty. on Other Location** field at the bottom shows a value and you can then look up and select the location from which the item should be supplied when you make the transfer order.  

    If a substitute exists for the demanded item, the **Substitute Exists** field is set to **Yes**, and you can then look up to the **Item Substitution Entries** page and select the substitute.  

7.  Select the **Reserve** check box if you want to make a reservation between the supply order you are creating and the demand line that it is created for. It is empty by default.  

    > [!NOTE]  
    >  You can only select this check box if the item has **Optional** or **Always** in the **Reserve** field on its item card.  

8.  In the **Qty. to Order** field, you can enter the quantity that will go on the supply order you are creating.   
    The default value is the same quantity as that in the **Needed Quantity** field. But you may decide to order more or less than this quantity based on your knowledge of the demand situation. If, for example, you see on the **Order Planning** page that several unrelated demand lines are for the same purchased item, and they are due around the same date, you can consolidate these by entering the total needed quantity in the **Qty. to Order** field of one line, and then delete the other, obsolete planning lines for that item.  

9.  In the **Due Date** and **Order Date** fields, you can enter the dates that should apply to the created supply orders.  

    These two fields are interrelated according to the **Default Safety Lead Time** field, which can be found on the **Manufacturing Setup** page. By default, the due date is the same as the demand date, but you can change this as you like.  

> [!NOTE]  
>  If you enter a date later than the demand date, you will receive a warning message.  

## To make supply orders  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planned Production Orders**, and then choose the related link. You can perform these steps for a planned, firm planned, or released production order.  
2.  Open the production order you want to plan for, and then choose the **Planning** action.  
3.  Place the cursor on a relevant planning line, and then choose the **Make Orders** action.  
4.  On the **Make Supply Orders** page, on the **Order Planning** FastTab, in the **Make Orders for** field, select one of the following options.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**The Active Line**|Make a supply order only for the line where the cursor is placed.|  
    |**The Active Order**|Make supply orders for all lines in the order where the cursor is placed.|  
    |**All Lines**|Make supply orders for all lines on the **Order Planning** page.|  

5.  On the **Options** FastTab, define what kind of supply orders, or requisition worksheet lines, should be made.  

    > [!NOTE]  
    >  The settings you last made on the **Make Supply Orders** page will be saved under your user ID so that they are the same the next time you use the page.  

6.  Choose the **OK** button to make the suggested supply orders or requisition worksheet lines.  

You have now planned for the unfulfilled demand by making respective supply orders. Details about specific work flows when using the **Order Planning** page would depend on a company’s internal policies.  

When you have finished your planning work on the **Order Planning** page, for example defined an alternative way to supply the quantity, you can proceed to create supply orders for one or more of the planning lines.  

> [!NOTE]  
>  The supply orders you create may introduce new dependent demand, for example for underlying production orders, and you should therefore choose **Calculate Plan** again to find and resolve this before moving down the list.  

## See Also  
[Planning](production-planning.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
