---
title: Bookmark a link to a page or report on your Role Center | Microsoft Docs
description: Learn how to add a link to your Role Center.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe
---

# Bookmark a Page or Report on Your Role Center
Using the bookmark icon, you can add an action that opens a page or report from the navigation menu of your Role Center. This allows you to quickly reach your favorite content or business tasks. You add the bookmark from the target page or report, meaning the screen that you want the link on the Role Center to open.

The bookmark icon is shown in the top right corner of a page and also in the **Tell Me** window where you can efficiently bookmark multiple pages or reports. If a bookmark already exists for the page, then the icon is dark, and the tooltip says "Bookmarked".

## To bookmark the target page
1. Open any page that you want a link for on your Role Center.
2. Choose the ![Bookmark](media/ui_bookmark_icon.png "Bookmark") icon.

An action named after the page is now added to the navigation menu on your Role Center.

## To bookmark the target report
1. Open any report request page that you want a link for on your Role Center.
2. Choose the ![Bookmark](media/ui_bookmark_icon.png "Bookmark") icon.

An action named after the report is now added to the navigation menu on your Role Center.

## To bookmark a page or report from the Tell Me window
1. Open the **Tell Me** window and enter, for example, **Sales Orders**.
2. Hover over the search result for the **Sales Orders** page or report, and then choose the ![Bookmark](media/ui_bookmark_icon.png "Bookmark") icon.

An action named after the page or report is now added to the navigation menu on your Role Center.


## Frequently Asked Questions  

- **Can I reorganize my bookmarks?**  
Yes. You can personalize your Role Center and move actions into a more optimal sequence or move them into existing groups or subgroups.  
Learn how to [Personalize Your Workspace](ui-personalization-user.md).

- **How do I remove a bookmark?**  
On the target page or report, choose the bookmark icon again to remove the involved action from your Role Center. You can also personalize your Role Center and temporarily hide actions without fully removing them.

- **Where do I find my bookmarks?**  
When adding a bookmark to a page or report, the new action is added to the top navigation menu on your current home screen (Role Center). If you happen to have many actions, you may need to activate the **More** button to display all of them because the new action is always appended at the end of those actions.
<!-- Should we add a screenshot here? -->

- **I don't have a bookmark icon. Is something wrong?**  
The ability to bookmark a page or report is one of many user personalization features in Business Central. If the bookmark icon is not displayed, it is likely that your administrator has disabled personalization.

- **Why can't I bookmark certain pages or reports?**  
Not all pages and reports can be bookmarked. When a page or report is run within some special context governed by the business application, the bookmark icon is not displayed. For example, pages that cannot be found in the **Tell Me** window but are launched from elsewhere will not display a bookmark icon. Similarly, report request pages that are only used to collect filters without running the report will not display a bookmark icon.

See technical details about [RunRequestPage](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/developer/methods-auto/report/reportinstance-runrequestpage-method) and [FilterPageBuilder](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/developer/methods-auto/filterpagebuilder/filterpagebuilder-data-type).

- **When clearing my personalization, will my bookmarks also be cleared?**  
Yes. Bookmarks reside in the navigation menu. If you clear changes to the navigation menu from any page, or clear all personalization on the Role Center, all your new actions will be permanently removed.

- **Why does the bookmark icon continue to indicate it is still not bookmarked?**  
When you add a bookmark, the new action is added to the navigation menu on the Role Center and subsequent visits to the page or report show a dark bookmark icon. If you personalize your Role Center and reorganize your actions by moving them into groups, the bookmark icon will no longer be dark and you can add another bookmark to that same page or report. This allows you add multiple actions to the same page or report and categorize them into different groups.

- **Why does my link to a report display a different report?**  
Some reports may be substituted by other reports after applying an extension to Business Central. When substitution occurs, the text of the new action is not updated and will continue to display the name of the original report, but navigate to the newer report. To correct the text of the new action, you can remove the new action and add it again.
<!-- For more information on report substitution, see this link UNAVAILABLE AT THIS TIME -->

- **Is bookmarking available for XMLports?**  
No. At this time, adding actions to open XMLports is not possible from the user interface.

- **Will my bookmarks be translated when I change my language in Business Central?**  
When you add a new action, any translated text that was available at the time is used when bookmarking. If new translated text is added later, then the new action will not include the newer translations.


## See Also
[Personalize Your Workspace](ui-personalization-user.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
