---
    title: Design Details - Order | Microsoft Docs
    description: This topic provides information about order-to-order links in a make-to-order environment.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, order
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Order
In a make-to-order environment, an item is purchased or produced to exclusively cover a specific demand. Typically it relates to A-items, and the motivation for choosing the order reordering policy can be that the demand is infrequent, the lead-time is insignificant, or the required attributes vary.  
  
The program creates an order-to-order link, which acts as a preliminary connection between the supply, a supply order or inventory, and the demand that it is going to fulfill.  
  
Apart from using the Order policy, the order-to-order link can be applied during planning in the following ways:  
  
* When using the Make-to-Order manufacturing policy to create multi-level or project type production orders (producing needed components on the same production order).  
* When using the Sales Order Planning feature to create a production order from a sales order.  
  
Even if a manufacturing company considers itself as a make-to-order environment, it might be best to use a Lot-for-Lot reordering policy if the items are pure standard without variation in attributes. As a result, the system will use unplanned inventory and only accumulates sales orders with the same shipment date or within a defined time bucket.  
  
## Order-to-Order Links and Past Due Dates  
Unlike most supply-demand sets, linked orders with due dates before the planning starting date are fully planned for by the system. The business reason for this exception is that specific demand-supply sets must be synchronized through to execution. For more information about the frozen zone that applies to most demand-supply types, see [Design Details: Dealing with Orders Before the Planning Starting Date](design-details-dealing-with-orders-before-the-planning-starting-date.md).  
  
## See Also  
[Design Details: Reordering Policies](design-details-reordering-policies.md)   
[Design Details: Planning Parameters](design-details-planning-parameters.md)   
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)