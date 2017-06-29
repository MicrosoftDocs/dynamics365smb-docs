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
# How to: Fill In the Revaluation Journal with the Batch Job
If you want to appreciate or depreciate an item or a specific item ledger entry, you must use the revaluation journal.  
  
 First, you must fill in the revaluation journal with information about the current, calculated value of the specified item or item ledger entry. You can do this [manually](../how-to-fill-in-revaluation-journals-manually.md) or use the **Calculate Inventory Value** batch job.  
  
### To fill in the revaluation journal with the batch job  
  
1.  In the **Search** box, enter **Revaluation Journal**, and then choose the related link.  
  
2.  As the calculation of inventory value can be rather time consuming, it is not desirable if the calculation is cancelled because of a precondition not met. Therefore, the **Calculate Inventory Value - Test** batch job can be used. This test report checks preconditions for the inventory value calculation.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Calculate Inventory Value**. The **Calculate Inventory Value** window opens.  
  
4.  On the **Item** FastTab, set a filter if you want to select a specific item number or select an item from a specific location or a specific variant of an item.  
  
5.  In the remaining fields, specify the conditions to use to create the journal lines.  
  
6.  Choose the **OK** button.  
  
 You can now revalue the selected item ledger entries. When you have filled in the revaluation journal, you can post the journal.  
  
 The value entries are created to reflect the revaluing. You can see these from the item card.  
  
## See Also  
 [Inventory Revaluation](../inventory-revaluation.md)   
 [How to: Enter New Values When Revaluing Items](../how-to-enter-new-values-when-revaluing-items.md)   
 [How to: Fill In Revaluation Journals Manually](../how-to-fill-in-revaluation-journals-manually.md)