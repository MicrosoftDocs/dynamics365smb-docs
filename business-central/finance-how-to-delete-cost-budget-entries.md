---
title: Delete cost budget entries
description: You use the Delete Cost Budget Entries batch job to cancel cost budget entries from the cost budget register.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 1115
ms.date: 07/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Delete cost budget entries

You use the **Delete Cost Budget Entries** batch job to cancel cost budget entries from the cost budget register.  

To prevent any gaps in the cost budget entries and cost register entries, you can't delete a single entry or a batch of entries in the middle of the list of register entries.  

## To delete a cost budget entry  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Cost Budget Entries**, and then choose the related link.  

    The **To Register No.** field contains the last register entry number and can't be changed.  

    You can use the **From Register No.** field to select a register entry number from which the deletion should begin.  
2. Choose the **OK** button to delete the selected cost budget entries.  

> [!NOTE]  
> To avoid an accidental deletion of cost budget entries, you can close register entries by marking the lines as **Closed** in the **Closed** field on the **Cost Budget Registers** page.  

## Related information

[Accounting for Costs](finance-manage-cost-accounting.md)    
[Creating Cost Budgets](finance-create-cost-budgets.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
