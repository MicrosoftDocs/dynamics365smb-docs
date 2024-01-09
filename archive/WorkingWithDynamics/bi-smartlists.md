---
title: Create Custom Queries using SmartLists
description: Learn about the capabilities of SmartList Designer and SmartList queries in Business Central.
author: brentholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: SmartList
ms.date: 10/01/2020
ms.author: bholtorf
ROBOTS: NOINDEX, NOFOLLOW
---
<!--# Create Custom Queries using SmartLists

Use SmartList Designer and SmartLists to create, manage and view queries using your Business Central data.  

The creation of queries can be done without writing code and the queries that are created can be exported and imported to make it easier to create once and use across tenants.

> [!Note]
> SmartLists and SmartList Designer functionality is only available in the online version of Business Central.

SmartList Designer is an app for [!INCLUDE [prodshort](includes/prodshort.md)] so that you can create queries on your Business Central data without requiring any type of customization or extension. SmartList Designer must be installed once in the [!INCLUDE [prodshort](includes/prodshort.md)] online tenant and can then be used by any user who has the relevant permissions. For more information, see [Get SmartList Designer](bi-smartlist-designer-setup.md).  

## Create a query

You can access SmartList Designer in two ways:

* In one of the 21 supported list pages, choose the **All** action, and then choose **New Query (SmartList)**.  

    The **SmartList Designer** page opens and is automatically loaded with data from the list page as well as any visible columns on the list page. This data source is your primary data source for the query.  

    > [!TIP]
    > If SmartList Designer has not yet been set up, you are automatically taken to the SmartList Designer Setup page.

    At this point, the minimum amount of information to create a query has been defined. You can preview the results, create the query, or extend the query definition as described below.  

* Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SmartList Designer**.

    The **SmartList Designer** page opens, but because it is not associated with a data source yet, you must specify the data source that you want to use as the primary data source.

  * Choose the **New** action from the context menu in the SmartList Designer app.  

    > [!Note]
    > If you have an existing query definition in progress, you will be prompted to save or discard the changes before continuing.

  * Choose the **Find Table** action to specify a primary data source for your query.

    SmartList Designer shows a list of all tables available in your [!INCLUDE [prodshort](includes/prodshort.md)]. Choose the table that you want to use as your primary data source for this query.

    Once the primary data source is selected, the query definition is loaded with the data from the first five fields from that data source. From here, the creation of the query is the same as the steps above when the data source was automatically selected for you.

### <a name="manage-fields"></a>Change the fields in the query

You can change the fields you want to make visible in your query. To modify the list of fields, choose the **Manage Fields** action, and then specify the fields that you want to make available in your query. You can also search to locate fields that you want to add to your query.

Once you have selected the fields that you want in the query, choose the **Apply** action. If you choose not to modify the field list, choose **Cancel**.

### Add an additional data source

If you want to add a data source, choose the **+ Table** action, and then choose a table from the list of tables that are related to the primary data source for the query. Once you choose a table, a table relationship between the primary data source and the new table is created. You can see an indicator for each successfully linked tables and fields.

> [!NOTE]
> Technically, the relationship between the two data sources is a *left outer join*. For more information, see the [Advanced links](#advanced-links) section.

#### Edit links between data sources

To modify an existing linked table or field, choose the ellipsis (...) in the upper corner of the data source that you want to modify the links on, and then choose the **Edit Link** action. In the **Link Fields** page, edit the relevant tables or fields, and then choose **Save**.

#### <a name="advanced-links"></a>Managing relationships between data sources

You can manually add table relationships, and you can create more advanced relationships between data sources. Following the same steps to add a table, select **Show All** below the table drop down list. This will display all available tables that can be added to the query definition. SmartList Designer will attempt to create a link between the data sources. If a link cannot be created, the **Link Fields** page opens.

Select the fields that you want to link between the data sources available. If a link cannot be create between the data sources, choose the **Cancel** action. If a link could not be created, you will receive a message indicating that a link could not be created and the data source you just added will be removed from the query definition.  

### Remove a data source

To remove a data source, choose the ellipsis (...) in the upper corner of the data source you want to remove. This opens a context menu where you can remove the data source.

### Apply filters on data

Select the filter icon on the data source you want to filter. The app will open a filter page that will enable you to select the fields you want to filter on, as well as what filter(s) you want to apply to the field.  

To apply filter, select a field from the data source, select a filter operator from the drop-down list and enter a filter value.  

> [!Tip]
> If you want to enter multiple filter values, use the `IN` operator. Choose the **+** icon next to the filter value to add additional filter values.  

To define additional filters on a selected field, choose the **+** icon on the left side of the page. There is no limit on the number of filters that can be applied to a field.  

> [!Tip]
> Each row will be treated as an `AND` clause between rows.

You may filter on more than one field within a selected data source. To add an additional field, choose the **Add Filter** icon in the lower left portion of the page. Repeat the previous steps to define the relevant filters for that field.

> [!Note]
> The applicable filter options will match what is available in Business Central. For more information, see [Sorting, Searching, and Filtering](ui-enter-criteria-filters.md).  

Once you have defined the filters you want to apply to a data source, choose OK. The application will return you to the query definition page and display a filter icon next to the fields that you have defined a filter for. To see the filter value, simply hover over the filter icon.

> [!Important]
> If you do not see a filter icon displayed on the query definition page, it could mean that you applied a filter on a field you did not make visible in your query. Filters can be applied to fields that are not displayed in the query definition.  

For more information, see the [Change the fields in the query](#manage-fields) section.

### Query preview

Once you have defined your query definition, you can preview the results before you save the query. Choose the **Preview** action to render the results of the query definition. When preview is selected, the results will render in a new browser tab. Business Central will open to the default company and render the results of the query.  

It is recommended that after you have reviewed the results that you close the SmartList page in Business Central.  

> [!Note]
> There are no refresh capabilities in Business Central for query definitions that have not been saved. You must do a preview after each change to your query definition in SmartList Designer so see accurate results.

> [!Tip]
> If you get a permission error during the preview, it means you have permissions to create the query but not to render a result set. For more information, see [SmartLists and permissions](bi-smartlist-designer-setup.md#permissions).

### Saving a query

Choose the **Save** button to save your query definition. You will be asked to provide an name and a category for your SmartList query.  

* Name

    The name is limited to 30 characters. If the name is longer than 30 characters, you receive an error message.  

* Category

    The category relates to the list page that you want the SmartList query to be visible from. There are 21 list pages available to choose from.  

Once the query has been saved, you will see a notification. If the query could not be saved, you will see an error message.  

> [!Tip]
> Once the SmartList query is saved, and you return to the list page that you started SmartList Designer from, you must refresh the list page before the new query is available in the navigation.

If you want to change the list page that the SmartList query is assigned to, choose the **Assign** action from the context menu **(…)** in the lower right. This action will be disabled if you have not yet saved your SmartList query.  

Once edits have been made to an existing SmartList query, the **Save As** action will become available in the context menu in the lower right.  

Use the **Save As** command to save the edits as a new query. SmartList query names must be unique. If you save a query with the same name as another query, you receive an error message.  

## Viewing a SmartList query

Once you save a SmartList query in the SmartList Designer page, it becomes available from the **All** drop down on the list page that you assigned it to. Users who have permission to view SmartList queries can then choose the query and view the results.  

> [!NOTE]
> A new SmartList query is not visible until the list page it is assigned to has refreshed. A refresh can be done by navigating away from the list page and then back to it, or by refreshing Business Central.

## Manage all available SmartList queries

You can manage all available queries in the **SmartList Management** page. By default, only a SUPER user will have permissions to this page. Other users can be granted permissions.  

The following table outlines the actions that you can choose in the **SmartList Management** page to help you create new SmartList queries or manage existing SmartList queries.

|Name|Description|
|----|-----------|
|**New**| Launches SmartList Designer without a data source pre-selected.|
|**Delete**| Delete one or more existing SmartList queries.|
|**Edit**| Opens SmartList Designer and visually displays the SmartList query definition.|
|**Preview**| Renders the result set for the SmartList query selected.|
|**Export**| Exports the selected SmartList queries to your downloads folder where they can be imported into another tenant. You must have permissions to export SmartList queries.|
|**Import**| Imports the SmartList query file into your Business Central tenant. You must have permissions to import SmartList queries.|
|**Assign Permissions**| Assign one or more SmartList queries to a user defined permission set.|
|**Navigation**| Create custom navigation to your SmartList query.|

The following table outlines the detailed information about each query in the **SmartList Management** page.

|Name|Description|
|----|-----------|
|**Object ID**| ID that is assigned to a SmartList query created with SmartList Designer. The object range from SmartList queries is 701,000 – 710,000.|
|**Name**| This is the name that was defined in SmartList Designer when the SmartList query was created.|
|**Description**| Short description of the SmartList query. By default, the description and name will have the same values.|
|**Assigned List Page**| Displays the list page the SmartList query is assigned to. This will be the query category assignment in SmartList Designer.|
|**Primary Table**| The data source that was defined as the first, or primary source, when the SmartList query was created in SmartList Designer.|
|**Last Modified by**| Displays name of user that that modified the SmartList query. If the SmartList query has never been modified, this will be the user that created the SmartList query.|
|**Last Modified**| Display the last date and time the SmartList query was modified. If the SmartList query has never been modified, this will be the date and time the SmartList query was created.|

### General Functionality

The **SmartList Management** page provides general functionality like other list pages in Business Central. You can search, filter, open in Excel, bookmark, and create custom views from this list.

The **SmartList Management** page has five default views:

* All
* Finance
* Inventory
* Purchasing
* Sales

SmartList queries are filtered into one of the views based upon the list page they were assigned to in SmartList Designer. To change the category, edit the query and reassign using the **Assign** action.

### Assigning permissions

In the **SmartList Management**, you can bulk-assign access to queries by assigning permissions. When you choose **Assign Permissions**, the **SmartList Permission Management** page opens and shows a list of all user-defined permission sets that you can then add the chosen queries to.  

> [!NOTE]
> You can add queries to a permission set in the **SmartList Permission Management** page, but you cannot remove queries from a permission set, and you cannot move queries from one permission set to another. To remove or move, you must use the permissions pages.

Once permissions are granted to a SmartList query, the users who have those permissions can see the SmartList query. However, they are not be able to view the results of the query if they do not have permissions to the underlying data sources that are defined for the query. For more information, see [SmartLists and Permissions](bi-smartlist-designer-setup.md#permissions).

### Export and import queries

Use the export/import functionality on the **SmartList Management** page to share SmartList queries across different tenants.

When you export one or more queries, Business Central will package up the queries and save them to the Downloads folder on your device. Only the query definition is exported, and not any data. Once the export completes, the **SmartList Export Results** page lists all the queries that were exported successfully and provides an error message for any queries that failed to export.

Similarly, when you import queries, the **SmartList Import Results** page lists all the queries that were imported successfully and provides an error message for any queries that failed to import.

> [!Tip]
> A common reason why a SmartList query will fail to import is that a data source that is found in the query definition does not exist in the tenant that the SmartList query is being imported into. This could happen when a query definition contains an extension data source and the tenant you are importing the query into does not have that same extension installed.

## Custom navigation

Custom navigation is used to create navigation points to other Business Central pages when rendering a SmartList query. A custom navigation is specific to the SmartList query it was created for and can be accessed from the **Navigation** action at the top of the query page. The **Navigation List** page shows any custom navigation that have been specified for this query.

### To create custom navigation for a query

1. Select **Create** at the top of the **Navigation List** page.
2. Provide a **name** for the custom action you are about to create. This name will be visible when rendering a SmartList query.  
3. Choose a **target page** from the lookup. A target page is the page that you want to navigate to when this SmartList query is viewed.
4. If you want a specific record to be returned on the target page, toggle the **Filter to Record** on. If not, select OK to close the page.
5. Select the **Linking Data Item** from the lookup. This will be the item you want displayed when the target page is opened.
6. Select **OK** to close the page.
7. Repeat these steps to create additional custom navigation.

You can edit or delete custom navigation in the **Navigation List** page.

If one or more custom navigation records are created for a given SmartList query, you can specify which of the actions must serve as the default navigation. The default action is taken when the hyperlink field in the SmartList query is selected while the SmartList query data is viewed.

## See also

[Get SmartList Designer](bi-smartlist-designer-setup.md)  
[Business Intelligence](bi.md) --> 
