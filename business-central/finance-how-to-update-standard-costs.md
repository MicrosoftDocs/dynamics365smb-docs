---
title: Update standard costs
description: You must periodically update the standard costs of components and roll the new costs up to the parent item.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 5841
ms.date: 07/30/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Update standard costs
You must periodically update the standard costs of components and roll the new costs up to the parent item. The process typically consists of the following four steps:  

1.  Update costs at the component and capacity levels. For more information, see the **Suggest Item Standard Cost** batch job.  
2.  Consolidate and roll up the component and capacity costs to calculate the total manufacturing or assembly cost of the items.  
3.  Implement the standard costs that are entered when you run the previous batch jobs. The standard costs don't take effect until they're implemented. Use the **Implement Standard Cost Changes** batch job, which updates the changes in the standard cost on items with the ones in the Standard Cost Worksheet table.  
4.  Implement the changes to update the **Unit Cost** field on the item card and perform inventory revaluation. For more information, see [Revalue Inventory](inventory-how-revalue-inventory.md).  

For more information, see [About Calculating Standard Cost](finance-about-calculating-standard-cost.md).
  
## To update standard costs

1.  Run the **Adjust Cost-Item Entries** batch job. To start the batch job, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Cost-Item Entries**, and then choose the related link. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Review the results and make changes as necessary.  
2.  Run the **Post Inventory Cost to G/L** batch job. To start the batch job, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Inventory Cost to G/L**, and then choose the related link. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Review the results and make changes as necessary.  
3.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Standard Cost Worksheet**, and then use one or more of the following actions:

    1.  Run the **Suggest Item Standard Cost** batch job.  
    2.  Review the results and make changes as necessary.  
    3.  Run the **Suggest Capacity Standard Cost** batch job.  
    4.  Review the results and make changes as necessary.
    5. Run the **Roll Up Standard Cost** batch job.
    6.  Review the results and make changes as necessary.
    7.  Run the **Implement Standard Cost Changes** batch job.  
4.  Review and post the **Item Revaluation Journals** page, which has been populated with entries from the previous steps in this process.  

## Related information

 [About Calculating Standard Cost](finance-about-calculating-standard-cost.md)   
 [Managing Inventory Costs](finance-manage-inventory-costs.md)   
 [Design Details: Costing Methods](design-details-costing-methods.md)   
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
