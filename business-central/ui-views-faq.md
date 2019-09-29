---
title: Frequently Asked Questions about List Views
description: Detailed information about saving filters as list views.
author: mikebcMSFT
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: list, filter, pane, views
ms.date: 09/30/2019
ms.author: mikebc

---
# List Views FAQ
This topic answers questions that our advanced users often ask about working with list views.  

### How do views handle expressions?
When saving a view that includes filters with expressions, such as date ranges, operators, keywords or filter tokens, the expression and not the resulting values is saved. For example, saving a view that filters on the **Created Date** field with the expression -1W..today will always find records relative to the current date, even when the view is accessed next month.

### Where are list views saved?
Similarly to hiding a field or reordering your navigation menu, list views are a part of user personalization and are stored in the database. Clearing all personalization on a list will also permanently remove your personal views along with any additional personalization such as hiding.

### Why don't I have a Save icon?
The save icon and options menu are not displayed alongside views in the filter pane if personalization is disabled for a user role. Users who do not have personalization enabled are still able to access views that are a standard part of the page, modify or create more filters.

### On which page types can I use list views?
Views are only available on list and worksheet pages.

### Are views also available on other form factors?
Yes. Any views you save on your desktop browser or desktop app will also be available on your tablet or smartphone. You cannot modify or personalize views on mobile devices.

### Are views always accessible?
The same views are available on a list page if you access it from the navigation menu, through the Tell Me window, or through a Url link to the list page. Views are not available in list parts, lookups or whenever a list page is displayed as a dialog.

### How do I return a view to its original filters after modifying them?
At the bottom of the filter pane, choose **Reset filters** to clear filter changes you have made to the view and return it to its original filtered fields and criteria.

### What is the difference between hiding and removing?
Removing a view will permanently delete that view. Hiding a view allows you to temporarily hide it from the filter pane, but you can unhide it again later by choosing **Show**.

### How can I share my views with others?
[!INCLUDE[d365fin](includes/d365fin_md.md)] does not provide a way to share the exact list view, but you can share your current filters so that other users can see a similar list of records. In your desktop browser, copy the Url and share it with your colleagues. Sharing filters is not guaranteed to give the recipient an identical set of filters that you see in your browser.

### Can I search for views in the Tell Me window?
No. The Tell Me window only displays search results for the page, but you are only a step away from getting to your favorite view once you navigate to the page.

### What is shared layout?


### Why do some views now allow me to save changes?


### What are the limitations of legacy views?
If your business application, extensions and customizations include legacy views 

### Others in my organization need similar list views. What can I do?

LINK TO CUSTOMIZATION DOCS


### I use multiple languages: how do I translate the name of the view?


### Do views with expressions work in all languages?
Expressions that only use symbols, such as '**|**' or **..**, are considered safe for users to access in any language. Any views with expressions that include letters, keywords or filter tokens will only work for the language they were authored in. 



### See Also  
[Finding Features and Information](ui-search.md)  
[Sorting, Searching and Filtering](ui-enter-criteria-filters.md)  
