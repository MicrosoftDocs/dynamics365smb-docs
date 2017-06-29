---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# Inventory Revaluation
The inventory value of an item can change over time, for example, as a result of damage or age.  
  
 If you want to change the inventory value of an item or a specific item ledger entry, you must use the revaluation journal.  
  
 You can also use the revaluation journal to correct incorrect posted documents.  
  
## Revalue Expected Costs  
 The program supports revaluation based on actual costs. However, for items using the **Standard** costing method, the program will also revalue based on expected costs. This means that for standard-cost items, inventory that is received but not invoiced can also be revalued. Accordingly, such expected inventory costs are also included in the [Calculate Inventory Value batch job](../FullExperience/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md) like any actual inventory costs, however, only if you select to calculate per item, by location, and by variant, on the **Options** FastTab of the batch job request page.  
  
 Note that by revaluing standard-cost items based on expected costs, the related [interim inventory accounts](../FullExperience/\($%20T_5813_5800%20Inventory%20Account%20\(Interim\)%20$\).md) will be affected.  
  
## The Revaluation Journal  
 In order to use the revaluation journal, you must consider the extent of the revaluation. There are two ways of filling in the journal with information about the current, calculated value of the specified item:  
  
-   You can [enter a line manually](../FullExperience/how-to-fill-in-revaluation-journals-manually.md) and link it to an item ledger entry in the **Applies-to Entry** field. This will change the inventory value of all units of this item ledger entry. It will also change the inventory value of the units that are applied to this item ledger entry, regardless of their posting date.  
  
-   You can fill in the journal by using the [Calculate Inventory Value batch job](../FullExperience/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md). This method allows you to specify exactly how the revaluation will change the inventory value of an item or item ledger entry. The revaluation will be valid for entries relating to this item or item ledger entry from the posting date of the revaluation journal.  
  
## See Also  
 Applies-to Entry   
 [How to: Fill In the Revaluation Journal with the Batch Job](../FullExperience/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md)   
 [Design Details: Expected Cost Posting](../FullExperience/design-details-expected-cost-posting.md)   
 [How to: Fill In Revaluation Journals Manually](../FullExperience/how-to-fill-in-revaluation-journals-manually.md)   
 [How to: Enter New Values When Revaluing Items](../FullExperience/how-to-enter-new-values-when-revaluing-items.md)