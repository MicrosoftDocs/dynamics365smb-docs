---
title: Why Can't I Personalize a Page | Microsoft Docs
description: Explains why you cannot personlaize a page and what yoo can do to unlock it so you can personalize it.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.date: 04/01/2020
ms.author: sgroespe

---
# Why a Page is Locked from Personalization

There are two conditions that prevent you from personalizing a page. Either the page is locked (as indicated by the ![Personalize Lock](media/personalization-lock-icon.png "Personalize lock")) icon or it is blocked (as indicated by the ![Personalization blocked](media/personalization-blocked-icon.png "Personalization blocked") icon).

## Locked from Personalizing

If there is a ![Personalize Lock](media/personalization-lock-icon.png "Personalize lock") icon in the **Personalizing** banner when you open a page, this means that you are currently prevented from making any more personalization changes to the page.

<!-- This is because we changed the way personalization works behind the scenes since the last time that you personalized the page. Unfortunately, the old way and new of doing things do not work together.

The page currently includes the last personalization changes that you made. If you want to continue personalizing the page, then you can choose the lock icon and then **Unlock**. Just be aware that if you choose to unlock the page, the current personalization of the page will be cleared, and you will have to start from scratch.
-->

There can be two reasons for this:

1. You have personalized the page before, but it was done using an earlier version of the product. We changed the way personalization works behind the scenes since the last time that you personalized the page. Unfortunately, the old way and new way of doing things do not work together.

2. Until now, you have only used the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] to personalize the page.

### Unlocking the Page

If you want to unlock a page and continue personalizing it, choose the ![Personalize Lock](media/personalization-lock-icon.png "Personalize lock") icon, and then choose the **Unlock** action.  

Before you unlock the page, be aware of the following:

- The current personalization of the page will be cleared. The page will go back to its original layout, and you will have to start from scratch.

- In the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)], the page will remain as-is and will not be affected by the new personalization changes made in the Business Central client. Going forward, the personalization in the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] and Business Central client will be completely separate from each other.

## Blocked from Personalizing

If there is a ![Personalization blocked](media/personalization-blocked-icon.png "Personalization blocked") icon in the **Personalizing** banner, this means that you are blocked from doing any personalization to the page.

<!-- Only text is translated, so removing this image for non-English UX reasons.  ![Personalize blocked](media/personalization-blocked.png "Personalize lock") -->

The reason for this is that the Role Center or role that is currently associated with your user account modifies this page specifically for your role. Contact your administrator for assistance. Alternatively, try switching to a Role Center that does include role-tailoring for this page. For more information, see [Change Basic Settings](ui-change-basic-settings.md).

## See Also
[Personalize Your Workspace](ui-personalization-user.md)  
[Customize Pages for Profiles](ui-personalization-manage.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
