---
title: Post the Year-End Closing entry
description: Describes how to open the journal you specified in the Close Income Statement batch job, and then review and post the year-end closing entry. 
author: brentholtorf
ms.topic: how-to
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.search.form: 100
ms.date: 08/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Post the Year-End Closing entry

After you use the **Close Income Statement** batch job to generate the year-end closing entry or entries, you must open the journal you specified in the batch job, and then review and post the entries.  

> [!TIP]
> Depending on your organizations work processes, you can choose to close or not close accounting periods and fiscal years in [!INCLUDE [prod_short](includes/prod_short.md)]. The following procedure assumes that you have closed the fiscal year using the *Accounting Periods* option, generated a year-end closing entry using the **Close Income Statement** batch job, and are now ready to post the year-end closing entry along with the offsetting equity account entries. Your organization can choose to work differently, such as post the year-end closing entry as part of closing the fiscal year.

## To post the year end closing entry

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.
2. On the **General Journals** page, in the **Batch Name** field, select the batch that contains the closing entries.
3. Review the entries.
4. To post the journal, choose the **Post** action.

> [!NOTE]  
> If an error is detected, an error message is displayed. If the posting is successful, the posted entries are removed from the journal. After posting is complete, an entry is posted to each income statement account so that its balance becomes zero and the year's result is transferred to the balance sheet.

## Related information

[Close Accounting Periods](year-close-account-periods.md)    
[Closing Books](year-close-books.md)    
[Close Income Statement](year-close-income-statement.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
