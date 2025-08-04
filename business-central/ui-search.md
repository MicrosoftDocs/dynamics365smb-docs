---
title: Finding Pages and Information
description: This article describes how to use search to find actions, pages, reports, documentation, and data, and other apps and consulting services.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: find, Tell Me, search
ms.search.form: TellMe, 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 10/01/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Finding pages and information with Tell Me

This article describes how the in-product search, *Tell me what you want to do*, can help you: 

* Quickly go to things like actions, pages, or reports.
* Search for specific data, either on a list page or in all of [!INCLUDE [prod_short](includes/prod_short.md)].
* Find [!INCLUDE [prod_short](includes/prod_short.md)] documentation about a subject you're interested in.

<!-- ![!VIDEO https://go.microsoft.com/fwlink/?linkid=2086048] -->

When you need help with finding something, use the ![Tell me what you want to do.](media/ui-search/search.png "Search for Page or Report") **Search** icon to search for it. You can also use <kbd>ALT</kbd>+<kbd>Q</kbd> to start a search.

When you start typing characters on the **Tell me what you want to do** page, [!INCLUDE[prod_short](includes/prod_short.md)] immediately displays matches. Results in the list change as you type more characters. If you notice that when you enter the word *product* and the results include *items*, that's because search uses synonyms and alternate search terms to make it easier to find actions, pages, and reports.

The column to the right indicates the general category of the result. For example, whether it opens a list page or is an administrative task.  

At the bottom of the **Tell me what you want to do** page, the **exploring pages and reports** action opens a feature overview that shows you all available features for your role or for all roles. Learn more at [Finding Pages with the Role Explorer](ui-role-explorer.md).

> [!TIP]  
> If you prefer to use your keyboard, use the <kbd>Tab</kbd> key and <kbd>Arrow</kbd> keys to choose an item in the results. If you select the <kbd>Enter</kbd> key on your keyboard without choosing a result, [!INCLUDE[prod_short](includes/prod_short.md)] opens the result that is listed first.

The **Tell me what you want to do** page categorizes results based on the data that you enter and the page you're working on. The following sections describe the categories.

## Find an action on the current page

The **On current page** section lets you find actions on the page you have open. For example, if the **Sales Quote** page is open and you type "customer," the section includes an action that opens the Customer Card page for the customer chosen on the sales quote.

> [!NOTE]  
> The list includes only actions that are available on the navigation bar at the top of the page. Actions on FastTabs aren't included.  

## Find a page or a task

The results in the **Go to Pages and Tasks** section provide access to other pages and let you perform tasks or look up information. If you use these pages often, you can choose the bookmark icon to add a link to any page onto your Role Center. Learn more in [Add a Page Action to Your Role Center](ui-bookmarks.md).

The pages and tasks that are listed depend on the user experience you chose for your company. The **Essentials** experience gives access to fewer pages and tasks than the **Premium** experience does. The first time you sign in, you use the **Essentials** experience. Learn more about user experiences in [Customizing Your [!INCLUDE[prod_short](includes/prod_short.md)] Experience](ui-experiences.md).

## Find a report or archived information

The **Go to Reports and Analysis** section offers access to reporting tools. For example, you can open the **Balance Sheet** report from the list, or access archived documents and other information.  

## Find a record or search the documentation

The **Search for \<keyword\>** section [!INCLUDE [prod_short](includes/prod_short.md)] offers a couple of ways to search:

* Use the **Search company data** action to search all pages in [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more about how the company data search works in [Search for a record in company data](ui-search-data.md).
* Use the **Search Help** action to find an article in the Business Central documentation that contains your keyword.

  > [!NOTE]  
  > Your search results won't include documentation for third-party extensions.

### Use Tell me what you want to do

Use the ![Tell me what you want to do.](media/ui-search/search.png "Search for Page or Report") **Search** icon to search for data across [!INCLUDE [prod_short](includes/prod_short.md)]. For example, you can find a customer by entering their name or address, or even find a specific record, such as a sales order. You can also use it to find information in our documentation.

Just enter at least three characters of a keyword, and then choose either **Search company data** or **Search Help**.

* If you search for data, results display on the **Search in company data** page, where they're sorted by type.  
* If you search in our Help, the **Help** pane offers links to articles that contain your keywords. You'll also get a snippet from the article that can help you decide whether it's what you're interested in.

> [!NOTE]
> For data, searching everything in [!INCLUDE [prod_short](includes/prod_short.md)] might take time. To speed up results, use the **Show tables to search** action to choose the tables and fields that you want to include in your searches. The tables and fields that you can choose from vary, depending on your Role Center. By default, all tables and fields are chosen, which can slow down the search. We recommend that you exclude as many tables and fields as you can.

[!INCLUDE [ui-how-search-works](includes/ui-how-search-works.md)]

## Get more functionality from apps

Our partner community is busily developing apps that add capabilities to [!INCLUDE[prod_short](includes/prod_short.md)]. The **Get from Microsoft AppSource** section lists apps for [!INCLUDE[prod_short](includes/prod_short.md)] that are available on Microsoft AppSource and are related to the keyword you searched for.

## Use search on list pages

It isn't related to Tell me what you want to do, but there's another way to search for specific data. When you're using a list page, you can use the ![Search list](media/ui-search/search-list.png "Search list icon") **Search** field in the left corner of list page headers to search for data on the page. The search applies only to the list you're viewing. Learn more about working with data on list pages in [Sorting, Searching, and Filtering Lists](ui-enter-criteria-filters.md#searching).  

> [!TIP]
> You can search for posted document lines, such as invoice lines, credit memo lines, shipment lines, and receipt lines. Search for the type of document lines that you want to find, and then bookmark the links to the documents on your home page for easy access to the original or a filtered view. Learn more in [Add a Page Action to Your Role Center](ui-bookmarks.md).

## Questions?

We've shown search to a range of stakeholders, noted the questions that they had in common, and turned our notes into a list of frequently asked questions. If you're interested, go to [Tell Me FAQ](ui-search-faq.md).

## Related information

[Work with Business Central](ui-work-product.md)  
[Add a Page Action to Your Role Center](ui-bookmarks.md)  
[Save and Personalize List Views](ui-views.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
