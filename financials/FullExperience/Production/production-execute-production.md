---
    title: Execute Production | Microsoft Docs
    description: When materials have been issued, the actual production operations can start and then be executed in the sequence defined by the production order routing.
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
# Execute Production
When materials have been issued, the actual production operations can start and then be executed in the sequence defined by the production order routing.  
  
 An important part of executing production, from a system point of view, is to post production output to the database to report progress and to update inventory with the finished items. Output posting can be done manually, by filling and posting journal lines after production operations. Or, it can be done automatically with the use of backward flushing. In that case material consumption is automatically posted along with output when the production order changes to finished.  
  
 As an alternative to the batch journal for output posting for multiple production orders, you can use the **Production Journal** window to post consumption and/or output for one production order line.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Print the job cards to be used by machine operators who will read work instructions and enter quantities for output posting.|Prod. Order - Job Card|  
|Record and post production output along with material and time consumption, for a single released production order line.|[How to: Register Consumption and Output](../how-to-register-consumption-and-output.md)|  
|Post time spent per operation.|[How to: Post Run Times](../how-to-post-run-times.md)|  
|Specify the warehouse bin where production output is placed - in warehouses without directed put-away and pick.|[How to: Assign Bin Codes on Journal Lines](../how-to-assign-bin-codes-on-journal-lines.md)|  
|Batch post produced items and production order value entries for one or more released production orders.|Output Journal|  
|Post the number of items produced in each finished operation which do not qualify as finished output, but as scrapped material.|[How to: Post Scrap Manually](../how-to-post-scrap-manually.md)|  
|Automatically request that warehouse workers put away finished goods by creating the inbound request document when refreshing the inventory or warehouse pick document.|"Create Inbound Request Field" in [Refresh Production Order Batch Job](../-$-b_99001025-refresh-production-order-$-.md)|  
|Put away finished goods according to the warehouse setup.|[How to: Put Away Production Output](../how-to-put-away-production-output.md)|  
|Set a production order to finished, automatically or manually, to indicate that all operations are complete and reported.|[How to: Finish Production Orders](../how-to-finish-production-orders.md)|  
|View information about completed production orders, such as posted entries, comments, and statistics.|[How to: View Finished Production Orders](../how-to-view-finished-production-orders.md)|  
|Calculate and adjust the cost of finished production items and consumed components for financial reconciliation.|[About Finished Production Order Costs](../about-finished-production-order-costs.md)|  
|Use the **Capacity Journal** window to post consumed capacities that are not assigned to a production order, such as maintenance work.|[How to: Post Capacities](../how-to-post-capacities.md)|  
  
## See Also  
 [Put Items Away](../put-items-away.md)   
 [Schedule Production Activities](../schedule-production-activities.md)   
 [Working with Product Name](../../../archive/WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)