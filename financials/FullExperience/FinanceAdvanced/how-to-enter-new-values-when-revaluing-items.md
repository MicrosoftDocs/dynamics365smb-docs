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
# How to: Enter New Values When Revaluing Items
If you want to change the inventory value of an item or that of a specific receipt, you must use the revaluation journal.  
  
 Before you can revalue an item, you must first fill in the journal with the calculated value of that item. You can then enter the new value of the item as described in the following procedure.  
  
### To enter a new values when revaluing item  
  
1.  In the **Search** box, enter **Revaluation Journal**, and then choose the related link.  
  
2.  Fill in the journal with calculated values. You can do this manually or using a batch job.  
  
3.  When you have filled in the journal, select the first line that you want to revalue.  
  
4.  In the **Unit Cost \(Revalued\)** field, enter the new unit cost, or enter the new total amount in the **Inventory Value \(Revalued\)** field.  
  
     The relevant fields are automatically updated. Note that the **Amount** field shows the actual change in inventory value for the selected item ledger entry. It calculates the difference between the **Inventory Value \(Calculated\)** field and the **Inventory Value \(Revalued\)** field.  
  
5.  When you have finished the revaluation, post the journal.  
  
 Repeat this procedure for all entries that you want to revalue.  
  
## See Also  
 [Inventory Revaluation](../DesignAndEngineering/inventory-revaluation.md)   
 [How to: Fill In the Revaluation Journal with the Batch Job](../DesignAndEngineering/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md)   
 [How to: Fill In Revaluation Journals Manually](../DesignAndEngineering/how-to-fill-in-revaluation-journals-manually.md)