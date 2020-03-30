---
title: How to Update Standard Costs | Microsoft Docs
description: You must periodically update the standard costs of components and roll the new costs up to the parent item.
services: project-madeira
documentationcenter: ''
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
# Update Standard Costs
You must periodically update the standard costs of components and roll the new costs up to the parent item. The process typically consists of the following four steps:  

1.  Update costs at the component and capacity levels. For more information, see the **Suggest Item Standard Cost** batch job.  
2.  Consolidate and roll up the component and capacity costs to calculate the total manufacturing or assembly cost of the items.  
3.  Implement the standard costs that are entered when you run the previous batch jobs. The standard costs do not take effect until they are implemented. For more information, see Implement Standard Cost Changes.  
4.  Implement the changes to update the **Unit Cost** field on the item card and perform inventory revaluation. For more information, see [Revalue Inventory](inventory-how-revalue-inventory.md).  

For more information, see [About Calculating Standard Cost](finance-about-calculating-standard-cost.md).  
## To update standard costs  
1.  Run the **Adjust Cost-Item Entries** batch job.  
2.  Run the **Post Inventory Cost to G/L** batch job.  
3.  Open the **Standard Cost Worksheet** and use one or more of the following functions:  

    1.  Run the **Suggest Item Standard Cost** batch job.  
    2.  Review the results and make changes as necessary.  
    3.  Run the **Suggest Capacity Standard Cost** batch job.  
    4.  Review the results and make changes as necessary.
    5. Run the **Roll Up Standard Cost** batch job.
    6.  Review the results and make changes as necessary.
    7.  Run the **Implement Standard Cost Changes** batch job.  
4.  Review and post the **Revaluation Journal** page, which has been populated with entries from the previous steps in this process.  

## See Also  
 [About Calculating Standard Cost](finance-about-calculating-standard-cost.md)   
 [Managing Inventory Costs](finance-manage-inventory-costs.md)   
 [Design Details: Costing Methods](design-details-costing-methods.md)
 [Finance](finance.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
