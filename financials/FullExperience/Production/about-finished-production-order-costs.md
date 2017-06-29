---
title: "About Finished Production Order Costs"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 4c9704ce-4da3-4c6d-9f30-19c2a951c75b
caps.latest.revision: 2
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# About Finished Production Order Costs
Finishing the production order is an important task in completing the costing lifecycle of the item that is being produced. Final costs, including variances in a standard cost environment, actuals in a FIFO, Average, or LIFO cost environment, are calculated using the **\($ B\_795 Adjust Cost \- Item Entries $\)** batch job, which allows for financial reconciliation of the costs of item production. For a production order to be considered for cost adjustment, the status must be **Finished**. It is therefore critical that upon completion, the status of a production order is changed to **Finished**.  
  
## Example  
 In a standard cost environment, when you consume material to produce an item, stated simply, the cost of the item plus labor and overhead go into WIP. When the item is produced, WIP is reduced by the amount of the standard cost of the item. Typically, these costs do not net to zero. So that these costs can net to zero, you must run the **\($ B\_795 Adjust Cost \- Item Entries $\)** batch job, noting that only production orders with the status of **Finished** will be considered for adjustment.  
  
## See Also  
 [\($ B\_795 Adjust Cost \- Item Entries $\)](../Finance/-$-b_795-adjust-cost-item-entries-$-.md)   
 [About Production Orders](../Production/about-production-orders.md)   
 [How to: Finish Production Orders](../Production/how-to-finish-production-orders.md)   
 [About Production Orders](../Production/about-production-orders.md)