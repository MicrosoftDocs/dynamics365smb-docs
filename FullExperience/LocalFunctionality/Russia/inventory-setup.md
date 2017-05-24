---
title: "Inventory Setup"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "item charges, assigning by weight or volume"
  - "inventory, posting corrections"
  - "correcting, item documents"
  - "assigning item charges, by weight or volume"
ms.assetid: eb1fc13e-c7d5-44c9-8538-151fcc86e3c2
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Inventory Setup
As part of inventory management, you can set up inventory to:  
  
-   Assign item charges on purchases from foreign countries\/regions based on weight or volume.  
  
-   Use the same column for original and corrective postings.  
  
## Item Charge Assignment in Purchase Documents  
 In Russia, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] can assign item charges on purchases from foreign countries\/regions based on weight or volume. For each item, in the **\($ N\_30 Item Card $\)** window, on the **Foreign Trade** FastTab, if the **\($ T\_27\_12401 Gross Weight Mandatory $\)** and **\($ T\_27\_12402 Unit Volume Mandatory $\)** fields are selected, you must fill in the **\($ T\_27\_41 Gross Weight $\)** and **\($ T\_27\_44 Unit Volume $\)** fields. When you suggest an item charge assignment on a purchase order, you must specify that the distribution principle, weight, and volume are added to the options to choose from. For more information, see [Suggesting Item Charge Assignment in Purchase Documents](../../Finance/suggesting-item-charge-assignment-in-purchase-documents.md).  
  
## Item Corrections  
 You can set up inventory to use the same column for original and corrective postings. This is often referred to as *red storno*.  
  
 You can use red storno posting to post corrections for the following inventory entries:  
  
-   Corrective entries in the item journal.  
  
-   Reversal of item documents such as item receipts and item shipments.  
  
-   Posting item revaluation or item reclassification journals.  
  
-   Periodic adjustments of item costs.  
  
 For more information, see [How to: Post Red Storno Corrections](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-post-red-storno-corrections.md).  
  
### Adjusting Item Cost  
 If you select the [\($ T\_313\_12415 Enable Red Storno $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12415-enable-red-storno-$-.md) field in the **\($ N\_461 Inventory Setup $\)** window, then negative deviations are posted according to red storno when you run the [\($ B\_795 Adjust Cost \- Item Entries $\)](../../Finance/-$-b_795-adjust-cost-item-entries-$-.md) batch job.  
  
## See Also  
 [Item Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/item-documents.md)   
 [Item Obligatory Acts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/item-obligatory-acts.md)   
 [How to: Post Red Storno Corrections](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-post-red-storno-corrections.md)   
 [\($ T\_313\_12408 Check Application Date $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12408-check-application-date-$-.md)   
 [\($ T\_313\_12410 Unit of Measure Mandatory $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12410-unit-of-measure-mandatory-$-.md)   
 [\($ T\_313\_12411 Automatic Posting Date Adjmt. $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12411-automatic-posting-date-adjmt.-$-.md)   
 [\($ T\_313\_12412 Employee No. Mandatory $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12412-employee-no.-mandatory-$-.md)   
 [\($ T\_313\_12414 Adjmt. Rounding as Correction $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12414-adjmt.-rounding-as-correction-$-.md)   
 [\($ T\_313\_12415 Enable Red Storno $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_313_12415-enable-red-storno-$-.md)