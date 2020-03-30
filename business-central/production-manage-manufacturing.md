---
    title: Execute Production | Microsoft Docs
    description: When demand is planned for and the materials have been issued according to production BOMs, then the actual production operations can start and be executed in the sequence defined by the production order routing.
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
# Manufacturing
> [!NOTE]
> Functionality described in this topic and sub topics is only visible in the user interface if you have the **Premium** experience. For more information, see [Change Which Features are Displayed](ui-experiences.md).

When demand is planned for and the materials have been issued according to production BOMs, then the actual production operations can start and be executed in the sequence defined by the production order routing.  

An important part of executing production, from a system point of view, is to post production output to the database to report progress and to update inventory with the finished items. Output posting can be done manually, by filling and posting journal lines after production operations. Or, it can be done automatically with the use of backward flushing. In that case material consumption is automatically posted along with output when the production order changes to finished.  

As an alternative to the batch journal for output posting for multiple production orders, you can use the **Production Journal** page to post consumption and/or output for one production order line.

Before you can begin to produce items, you must make various setup, such as work centers, routings, and production BOMs. For more information, see [Setting Up Manufacturing](production-configure-production-processes.md).

The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Understand how production orders work.|[About Production Orders](production-about-production-orders.md)|
|Create production orders manually.|[Create Production Orders](production-how-to-create-production-orders.md)|
|Outsource all or selected operations in a production order to a subcontractor.|[Subcontract Manufacturing](production-how-to-subcontract-manufacturing.md)|
|Record and post production output along with material and time consumption for a single released production order line.|[Post Consumption and Output for One Released Production Order Line](production-how-to-register-consumption-and-output.md)|  
|Batch post the quantity of components used per operation in a journal that can processes multiple planned production orders.|[Batch Post Consumption](production-how-to-post-consumption.md)|
|Post the quantity of finished items and the time spent per operation in a journal that can processes multiple released production orders.|[Batch Post Output and Run Times](production-how-to-post-output-quantity.md)|
|Undo output, for example because of a data entry error occurred and incorrect amount.  |[Reverse Output Posting](production-how-to-reverse-output-posting.md)|  
|Post the number of items produced in each finished operation which do not qualify as finished output, but as scrapped material.|[Post Scrap](production-how-to-post-scrap.md)|
|View the shop floor load as a result of planned and released production orders.|[View the Load in Work and Machine Centers](production-how-to-view-the-load-on-work-centers.md)|      
|Use the **Capacity Journal** page to post consumed capacities that are not assigned to a production order, such as maintenance work.|[Post Capacities](production-how-to-post-capacities.md)|  
|Calculate and adjust the cost of finished production items and consumed components for financial reconciliation.|[About Finished Production Order Costs](finance-about-finished-production-order-costs.md)|  

## See Also  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
