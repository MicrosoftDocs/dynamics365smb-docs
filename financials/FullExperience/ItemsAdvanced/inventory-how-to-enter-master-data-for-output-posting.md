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
# How to: Enter Master Data for Output Posting
To post work progress automatically, you must assign a flushing method to the machine center or the work center.  
  
### To enter master data for output posting  
  
1.  In the **Search** box, enter **Machine Centers**, and then choose the related link.  
  
2.  Open the relevant machine center card from the list.  
  
3.  On the **Posting** FastTab, fill in the **Flushing Method** field. You can choose from the following options.  
  
    |Flushing Method|Description|  
    |---------------------|-----------------|  
    |**Manual**|Manual posting of consumption in the output journal.|  
    |**Forward**|Automatic posting of planned run time and output quantity upon releasing the production order.|  
    |**Backward**|Automatic posting of planned run time and output quantity upon finishing the production order.|  
  
4.  Repeat these steps on the **Posting** FastTab of the **Work Center** card.  
  
## See Also  
 [How to: Post Output Quantity](../how-to-post-output-quantity.md)   
 [How to: Post Run Times](../how-to-post-run-times.md)