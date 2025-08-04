---
title: How to Apply General Ledger Entries in Closed Periods
description: Learn to post entries after a closed posting period, even without performing any actual postings during that time.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: closed period, apply entries, apply general ledger entries, Norwegian version
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Apply general ledger entries in closed periods

[!INCLUDE[prod_short](../../includes/prod_short.md)] allows you to post entries after a posting period is closed, even if no actual posting is performed during that period. You can also choose the users who will make these entries.  

## Apply an entry in a closed period  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **General** FastTab, select the **Application always Allowed** checkbox to apply entries outside the allowed posting period.  

    > [!NOTE]  
    > By default, the **Application always Allowed** checkbox isn't selected.  

1. Choose the **OK** button.  
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.  
1. On the **User Setup** page, select the **Application always Allowed** checkbox for each user who can apply entries to a closed period.  
1. Choose the **OK** button.  

## Related information

[Norway Local Functionality](norway-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
