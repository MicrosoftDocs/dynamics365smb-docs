---
title: "About Searching and Filtering in Business Central"
description: "Answers frequently-asked questions about Search and Filter."
author: mikebcMSFT
ms.service: dynamics365-business-central
ms.topic: article
ms.reviewer: edupont04
ms.search.keywords: keyboarding, productivity, how do i, filter pane
ms.date: 04/01/2020
ms.author: mikebc
---

# Searching and Filtering FAQ
This article answers common questions you might have about searching and filtering.

## Is there a difference between searching and filtering?
Yes.
- Search is simple and broad: it matches records that contain the search text across any visible fields on the page, and is case insensitive.
- Filtering is highly flexible and can be applied to specific fields, including those not visible on the page: it displays records with exact, case-sensitive matches, but can be adjusted with powerful search symbols, tokens, and formulas. For more information on how to use these features, see [Sorting, Searching, and Filtering](ui-enter-criteria-filters.md).

## Is there a keyboard experience for search and filter?
Search and filter have been highly optimized for users who prefer mouse-free interaction to work efficiently with their data. There are a variety of shortcut keys that can be used in sequence to work at high speed. For more information see [Keyboard Shortcuts](keyboard-shortcuts.md#KeyboardFilter).

## Is the filter pane available on all lists?
The filter pane is available on pages where the list is the primary content on the page, such as worksheets and list pages, including lists reachable from the navigation bar. The filter pane is not yet available for lists that are displayed as parts, such as FactBoxes or Role Center parts. When a list is embedded on a page, such as sales lines on a sales order, the filter pane is available when focusing on that list using the focus mode button. For more information, see [Focusing on Line Items](ui-enter-data.md#Focus).

## How can I save my filters?
Your filters and adjustments to predefined filters are remembered throughout the session (while you remain signed in), even if you navigate away from the page. You can permanently save filters as a named view of the list by choosing the ![Save View](media/save_view_icon.png "Save View") icon in the filter pane. For more information, see [List Views FAQ](ui-views-faq.md). Note that, unlike filters, search text is not remembered when you navigate away from a page and is not saved when you save a view.

On report request pages, you can also save filters or use predefined filters. For more information, see [Using Saved Settings](ui-work-report.md#SavedSettings).

## Is this the same as Advanced Filters and Limit Totals in Microsoft Dynamics NAV?
[!INCLUDE[d365fin](includes/d365fin_md.md)] builds upon these popular features and delivers a modern and highly usable experience for finding and analyzing your data. With more keyboard shortcuts and the introduction of search, [!INCLUDE[d365fin](includes/d365fin_md.md)] surpasses the functionality provided in Dynamics NAV.  

## Can I search and filter using the companion apps and Outlook AddIn?
On different display targets such as mobile devices or in Outlook, you can search in lists but cannot filter on individual fields in most cases.

## Will Microsoft extend the filter pane experience?
At Microsoft, we're constantly listening to feedback from our diverse community of users and acting upon the top community suggestions. If you are interested in extending the filter pane to more form factors and more types of lists, or have a great idea on how to improve it, add an idea or vote for existing ideas at [aka.ms/BusinessCentralIdeas](https://aka.ms/businesscentralideas).

## Can I do anything about the "Searching for rows is taking too long" message?

There is a time-limit on how a long a search operation can take. First, try changing the search criteria and search again. If you are using [!INCLUDE[prodshort](includes/prodshort.md)] on-premises, contact your system administrator, because an administrator can increase the time-limit for searches.

As an on-premises administrator, you increase the time-limit on searches by changing the **Search Timeout** setting of [!INCLUDE[prodshort](includes/prodshort.md)] server. For more information, see [Configuring Business Central Server](/dynamics365/business-central/dev-itpro/administration/configure-server-instance?#Database) in the Business Central Developer and IT Pro Help.

## See also
[Sorting, Searching, and Filtering](ui-enter-criteria-filters.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Finding Pages with the Role Explorer](ui-role-explorer.md)  
[Getting Started](product-get-started.md)  
