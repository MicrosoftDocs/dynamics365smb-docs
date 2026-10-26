---
title: Apply Entries in Closed VAT Periods in Norway
description: Allow customer and vendor entry applications in closed Norwegian VAT periods for all users or selected users, while retaining posting date restrictions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: closed period, apply entries, apply general ledger entries, Norwegian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Apply entries in closed VAT periods

[!INCLUDE[prod_short](../../includes/prod_short.md)] can allow customer and vendor entry applications in a closed VAT period. This setting doesn't apply or unapply general ledger entries, reopen the VAT period, or override the allowed posting dates.

To allow applications for all users, select **Application always Allowed** on **General Ledger Setup**. To allow only selected users, leave that field cleared and select the field for those users on **User Setup**. You don't need to enable both settings.

## Apply an entry in a closed period  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
1. On the **General** FastTab, select **Application always Allowed** to allow applications in closed VAT periods for all users. To allow only selected users, leave this field cleared.

    > [!NOTE]  
    > By default, the **Application always Allowed** checkbox isn't selected.  

1. Choose the **OK** button.  
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **User Setup**, and then choose the related link.  
1. If the setting on **General Ledger Setup** is cleared, select **Application always Allowed** on **User Setup** for each user who can apply entries in closed VAT periods.
1. Choose the **OK** button.  

## Related information

[Norway Local Functionality](norway-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
