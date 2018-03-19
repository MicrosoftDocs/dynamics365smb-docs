---
    title: How to Track Relations Between Demand and Supply | Microsoft Docs
    description: From any supply or demand document in the so-called order network, you can track the order demand (tracked quantity), forecast, blanket sales order, or planning parameter (untracked quantity) that has given rise to the planning line in question.
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
# Track Relations Between Demand and Supply
From any supply or demand document in the so-called order network, you can track the order demand (tracked quantity), forecast, blanket sales order, or planning parameter (untracked quantity) that has given rise to the planning line in question.

The planning worksheets also offers supporting planning information about non-order entities to help the planner obtain an optimal supply plan. For more information, see the "Untracked Planning Elements" section.

## To track linked items
Order tracking shows how sales orders, production orders, and purchase orders are related to the manufacturing order through the planning and reservation systems.

The following describes how to track linked items on a firm planned production order. The steps are similar for all other order types, and from planning worksheet lines.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Firm Planned Prod. Order**, and then choose the related link.
2. Open the relevant firm planned production order from the list.
3. On the **Lines** FastTab, choose the **Functions** action, and then choose the **Order Tracking** action.

The lines in the **Order Tracking** display the documents that are related to the current production order line.

## Untracked Planning Elements
The **Untracked Planning Elements** window opens when you choose the **Untracked Qty.** field in the **order Planning** window. It serves two purposes:

1. To hold information about untracked quantities displayed when the user looks up from the Order Tracking window to see untracked quantities.
2. To hold warning messages displayed when the user chooses the **Warning** icon in the **Planning Worksheet** window.

The window contains entries which account for an untracked surplus quantity in order tracking network. These entries are generated during the planning run and explain where the untracked surplus quantity in the order tracking lines came from. This untracked surplus can come from:

- Production forecast
- Blanket orders
- Safety stock quantity
- Reorder point
- Maximum inventory
- Reorder quantity
- Maximum order quantity
- Minimum order quantity
- Order multiple
- Dampener (% of lot size)

## See Also  
[Planning](production-planning.md)   
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Reservation, Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
