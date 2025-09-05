---
title: Reverse Output Posting
description: There are times when output posting must be reversed. This topic outlines the procedure for reversing output posting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 5510
ms.date: 06/22/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Reverse Output Posting

There are times when output posting must be reversed. An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.  

## To reverse an output posting

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Output Journal**, and then choose the related link. Select your batch.  
2. Fill in the fields as necessary. For more information, see [Batch Post Output and Run Times](production-how-to-post-output-quantity.md).
3. In the **Applies-To Entry** field, select the associated item ledger entry. This reverses the capacity and item ledger entries.  
4. Post the reversal by posting the journal.  

The output journal entries are posted to the item ledger as a positive adjustment.  

## Related information

 [Manufacturing](production-manage-manufacturing.md)
 [Setting Up Manufacturing](production-configure-production-processes.md)  
 [Planning](production-planning.md)  
 [Inventory](inventory-manage-inventory.md)  
 [Purchasing](purchasing-manage-purchasing.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
