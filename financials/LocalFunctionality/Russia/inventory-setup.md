---
    title: Inventory Setup | Microsoft Docs
    description: As part of inventory management, you can set up inventory to:
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
# Inventory Setup
As part of inventory management, you can set up inventory to:  
  
-   Assign item charges on purchases from foreign countries/regions based on weight or volume.  
  
-   Use the same column for original and corrective postings.  
  
## Item Charge Assignment in Purchase Documents  
 In Russia, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/suggesting-item-charge-assignment-in-purchase-documents.md).  
  
## Item Corrections  
 You can set up inventory to use the same column for original and corrective postings. This is often referred to as *red storno*.  
  
 You can use red storno posting to post corrections for the following inventory entries:  
  
-   Corrective entries in the item journal.  
  
-   Reversal of item documents such as item receipts and item shipments.  
  
-   Posting item revaluation or item reclassification journals.  
  
-   Periodic adjustments of item costs.  
  
 For more information, see [How to: Post Red Storno Corrections](how-to-post-red-storno-corrections.md).  
  
### Adjusting Item Cost  
 If you select the Enable Red Storno field in the **Inventory Setup** window, then negative deviations are posted according to red storno when you run the Adjust Cost - Item Entries batch job.  
  
## See Also  
 [Item Documents](item-documents.md)   
 [Item Obligatory Acts](item-obligatory-acts.md)   
 [How to: Post Red Storno Corrections](how-to-post-red-storno-corrections.md)   
 Check Application Date   
 Unit of Measure Mandatory   
 Automatic Posting Date Adjmt.   
 Employee No. Mandatory   
 Adjmt. Rounding as Correction   
 Enable Red Storno