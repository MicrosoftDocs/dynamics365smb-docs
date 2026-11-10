---
title: Why a Page Is Locked from Personalization
description: Learn why a Business Central page can be locked or blocked from personalization, how to unlock it, and when to contact your administrator.
author: brentholtorf
ms.topic: troubleshooting
ms.devlang: al
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.date: 11/10/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Why a page is locked from personalization

The **Personalizing** banner can indicate that a page is locked, with the lock icon :::image type="icon" source="media/personalization-lock-icon.png":::, or blocked, with the blocked icon :::image type="icon" source="media/personalization-blocked-icon.png":::.

## Locked from personalizing

If there's a lock icon :::image type="icon" source="media/personalization-lock-icon.png"::: in the **Personalizing** banner when you open a page, you're currently prevented from making any more personalization changes to the page.

<!-- This is because we changed the way personalization works behind the scenes since the last time that you personalized the page. Unfortunately, the old way and new of doing things do not work together.

The page currently includes the last personalization changes that you made. If you want to continue personalizing the page, then you can choose the lock icon and then **Unlock**. Just be aware that if you choose to unlock the page, the current personalization of the page will be cleared, and you will have to start from scratch.
-->

There can be two reasons:

1. You've personalized the page before, but it was done using an earlier version of the product. We changed the way personalization works behind the scenes since the last time that you personalized the page. Unfortunately, the old way and new way of doing things don't work together.

2. Until now, you've only used the deprecated [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] to personalize the page.

### Unlock the page

If you want to unlock a page and continue personalizing it, choose the lock icon :::image type="icon" source="media/personalization-lock-icon.png":::, and then choose the **Unlock page** action.

> [!CAUTION]
> The current personalization of the page will be cleared. The page will go back to its original layout, and you'll have to start from scratch.  

## Blocked from personalizing

If there's a blocked icon :::image type="icon" source="media/personalization-blocked-icon.png"::: in the **Personalizing** banner, you're blocked from doing any personalization to the page.

<!-- Only text is translated, so removing this image for non-English UX reasons.  ![Personalize blocked.](media/personalization-blocked.png "Personalize lock") -->

One reason is that your current profile applies a legacy customization to the page. A current profile customization doesn't by itself block personalization. Contact your administrator for assistance. Alternatively, try switching to a role that doesn't apply the legacy customization. For more information, see [Change Basic Settings](ui-change-basic-settings.md).

## Related information

[Personalize Your Workspace](ui-personalization-user.md)  
[Customize Pages for Profiles](ui-personalization-manage.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
