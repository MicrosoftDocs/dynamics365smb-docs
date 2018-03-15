---
    title: Design Details - Closing Demand and Supply | Microsoft Docs
    description: This topic provides a suggestion for what to do after you perform supply balancing procedures.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, planning, example, closing, supply
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Closing Demand and Supply
When the supply balancing procedures have been performed, there are three possible end situations:  
  
* The required quantity and date of the demand events have been met and the planning for them can be closed. The supply event is still open and may be able to cover the next demand, so the balancing procedure can start over with the current supply event and the next demand.  
* The supply order cannot be modified to cover all of the demand. The demand event is still open, with some uncovered quantity that may be covered by the next supply event. Thus the current supply event is closed, so the balancing act can start over with the current demand and the next supply event.  
* All of the demand has been covered; there is no subsequent demand (or there has been no demand at all). If there is any surplus supply, it may be decreased (or canceled) and then closed. It is possible that additional supply events exist further along in the chain, and they should also be canceled.  
  
Last, the planning system will create an order tracking link between the supply and the demand.  
  
## Creating the Planning Line (Suggested Action)  
If any action – New, Change Quantity, Reschedule, Reschedule and Change Quantity, or Cancel – is suggested to revise the supply order, the planning system creates a planning line in the planning worksheet. Due to order tracking, the planning line is created not only when the supply event is closed, but also if the demand event is closed, even though the supply event is still open and may be subject to additional changes when the next demand event is processed. This means that when first created, the planning line may be changed again.  
  
To minimize database access when handling production orders, the planning line can be maintained in three levels, while aiming to perform the least demanding maintenance level:  
  
* Create only the planning line with the current due date and quantity but without the routing and components.  
* Include routing: the planned routing is laid out including calculation of starting and ending dates and times. This is demanding in terms of database accesses. To determine the ending and due dates, it may be necessary to calculate this even if the supply event has not been closed (in the case of forward scheduling).  
* Include BOM explosion: this can wait until just before the supply event is closed.  
  
This concludes the descriptions of how demand and supply is loaded, prioritized, and balanced by the planning system. In integration with this supply planning activity, the system must ensure that the required inventory level of each planned item is maintained according to its reordering policies.  
  
## See Also  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)   
[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)