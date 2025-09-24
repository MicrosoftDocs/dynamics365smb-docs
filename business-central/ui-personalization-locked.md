---
title: Why a Page is Locked from Personalization
description: You might be blocked from personalizing a page. Read here about what you can do to unlock it so you can personalize it.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.search.form: 
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Why a Page is Locked from Personalization

There are two conditions that prevent you from personalizing a page. Either the page is locked (as indicated by the ![Personalize Lock.](media/personalization-lock-icon.png "Personalize lock")) icon or it's blocked (as indicated by the ![Personalization blocked.](media/personalization-blocked-icon.png "Personalization blocked") icon).

## Locked from Personalizing

If there's a ![Personalize Lock.](media/personalization-lock-icon.png "Personalize lock") icon in the **Personalizing** banner when you open a page, you're currently prevented from making any more personalization changes to the page.

<!-- This is because we changed the way personalization works behind the scenes since the last time that you personalized the page. Unfortunately, the old way and new of doing things do not work together.

The page currently includes the last personalization changes that you made. If you want to continue personalizing the page, then you can choose the lock icon and then **Unlock**. Just be aware that if you choose to unlock the page, the current personalization of the page will be cleared, and you will have to start from scratch.
-->

There can be two reasons:

1. You've personalized the page before, but it was done using an earlier version of the product. We changed the way personalization works behind the scenes since the last time that you personalized the page. Unfortunately, the old way and new way of doing things don't work together.

2. Until now, you've only used the bow deprecated [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] to personalize the page.

### Unlocking the Page

If you want to unlock a page and continue personalizing it, choose the ![Personalize Lock](media/personalization-lock-icon.png "Personalize lock") icon, and then choose the **Unlock** action.  

> [!CAUTION]
> The current personalization of the page will be cleared. The page will go back to its original layout, and you'll have to start from scratch.  

## Blocked from Personalizing

If there's a ![Personalization blocked](media/personalization-blocked-icon.png "Personalization blocked") icon in the **Personalizing** banner, you're blocked from doing any personalization to the page.

<!-- Only text is translated, so removing this image for non-English UX reasons.  ![Personalize blocked.](media/personalization-blocked.png "Personalize lock") -->

The reason is that the Role Center or role that is currently associated with your user account modifies this page specifically for your role. Contact your administrator for assistance. Alternatively, try switching to a Role Center that does include role-tailoring for this page. For more information, see [Change Basic Settings](ui-change-basic-settings.md).

## Related information

[Personalize Your Workspace](ui-personalization-user.md)  
[Customize Pages for Profiles](ui-personalization-manage.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
