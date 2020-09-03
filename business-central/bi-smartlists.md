---
title: SmartLists | Microsoft Docs
description: Learn about the capabilities of SmartList Designer and SmartList queries.
author: bmeier90

ms.service: dynamics365-business-central
ms.topic: article
ms.reviewer: edupont
ms.search.keywords: SmartList
ms.date: 09/03/2020
ms.author: bmeier

---
# Create Custom Queries using SmartLists

Use SmartList Designer and SmartLists to create, manage and view queries using your Business Central data.  

The creation of queries can be done without writing code and the queries that are created can be exported and imported to make it easier to create once and use across tenants.

> [!Note]
> SmartLists and SmartList Designer functionality is only available in the online version of Business Central.

SmartList Designer is an app for [!INCLUDE [prodshort](includes/prodshort.md)] so that you can create queries on your Business Central data without requiring any type of customization or extension. SmartList Designer must be installed once in the [!INCLUDE [prodshort](includes/prodshort.md)] online tenant and can then be used by any user who has the relevant permissions. For more information, see [Get SmartList Designer](setup-smartlist-designer.md).  

## Creating a query

You may launch SmartList Designer two ways. The first option is to navigate to one of the 21 different list page SmartList Designer can be launched from.
From the list page, select the **All** drop down button at the top of the list and select **New Query (SmartList)**.  

The SmartList Designer page will open and automatically select the data source related to the list page you initiated SmartList Designer from as well as any visible columns on the list page. This will be considered your Primary data source for the query.  

> [!Important]
> If SmartList Designer has not yet been set up, the user will be automatically taken to the SmartList Designer Setup page.

At this point, the minimum amount of information to create a query has been defined. You may preview the results, create the query, or extend the query definition.  

The second option for launching SmartList Designer is to search for SmartList Designer and select the related link or by selecting New from the SmartList Management page.
SmartList Designer will open, but instead of auto populating the Primary data source and columns, you will need to manually select the data source you want to use as the Primary data source. Once the primary data source is selected, the first 5 fields from that data source will auto populate the query definition.

### Manage Fields

The **Manage Fields** action at the bottom of the list of fields will enable you to change the fields you want to make visible in your query. The list of fields will auto-populate depending on where SmartList Designer was launched from.  

To modify that list, select **Mange Fields** and select/unselect the fields you want to make available in your query by marking or unmarking the checkbox next to each field. You may also do a search to locate fields you may want to add to your query.

Once you have the fields selected that you want in the query, select **Apply**. If you choose not to modify the field list, choose **Cancel**.

### Adding a table

To add another data source to your query, select **+ Table**. You will be presented with a list of tables that are related to the primary data source. Once a table is selected, there is no need to define a relationship between the tables as this is automatically done for you. All successfully linked tables and fields will have an indicator next to them.

> [!NOTE]
> A left outer join is created automatically between data sources. See the [Advanced links](#advanced-links) section for instructions on how to modify the default link.

### Advanced Links

In the instance where you want to relate two data sources they may not have a relationship defined, use the advanced link functionality. Following the same steps to add a table, select **Show All** below the table drop down list. This will display all available tables that can be added to the query definition. SmartList Designer will attempt to create a link between the data sources. If a link cannot be created, the **Link Fields** page opens.

Select the fields that you want to link between the data sources available. If a link cannot be create between the data sources, choose the **Cancel** action. If a link could not be created, you will receive a message indicating that a link could not be created and the data source you just added will be removed from the query definition.  

### Edit Links

To modify an existing linked table or field, choose the ellipsis (...) in the upper corner of the data source you want to modify the links on. Select **Edit Link** from the context menu. The Link Fields screen will appear and display the tables and fields currently linked. Edit the tables or fields you would like to update and select **Save**.

### Removing a table

To remove a data source, choose the ellipsis (...) in the upper corner of the data source you want to remove. This will open a context menu that will enable you to remove the data source.

### Apply Filter

Select the filter icon on the data source you want to filter. The app will open a filter page that will enable you to select the fields you want to filter on, as well as what filter(s) you want to apply to the field.  

To apply filter, select a field from the data source, select a filter operator from the drop-down list and enter a filter value.  

> [!Tip]
> If you want to enter multiple filter values, use the IN operator. Select the + icon next to the filter value to add additional filter values.  

To define additional filters on a selected field, choose the **+** icon on the left side of the page. There is no limit on the number of filters that can be applied to a field.  

> [!Tip]
> Each row will be treated as an AND clause between rows.

You may filter on more than one field within a selected data source. To add an additional field, choose the **Add Filter** icon in the lower left portion of the page. Repeat the previous steps to define the relevant filters for that field.

> [!Note]
> The applicable filter options will match what is available in Business Central. For more information, see [Sorting, Searching, and Filtering](ui-enter-criteria-filters.md).  

Once you have defined the filters you want to apply to a data source, select OK. The application will return you to the query definition page and display a filter icon next to the fields that you have defined a filter for. The see the filter value, simply hover over the filter icon.

> [!Important]
> If you do not see a filter icon displayed on the query definition page, it could mean that you applied a filter on a field you did not make visible in your query. See Manage  > Fields. Filters can be applied to fields that are not displayed in the query definition.

### Query preview

Once you have defined your query definition, you may preview the results before saving it. Select the Preview button to render the results of the query definition. When preview is selected, the results will render in a separate instance, browser tab, of Business Central. Business Central will open to the default company and render the results of the query.  

It is recommended that after you have reviewed the results that you close the SmartList page in Business Central.  

> [!Note]
> There are no refresh capabilities in Business Central for query definitions that have not been saved. You must do a preview after each change to your query definition in   >SmartList Designer so see accurate results.

> [!Tip]
> If you get a permission error when Preview is selected it means you have permissions to create the query but not to render a result set. For more information, see [SmartLists and permissions](setup-smartlist-designer.md#smartlists-and-permissions).

### Saving a Query

Choose the **Save** button to save your query definition. You will be asked to provide and name and category for your SmartList query.  

The name is limited to 30 characters. You will receive an error message if the name you defined is longer than 30 characters.  

The category relates to the list page you want the SmartList query to be visible from. There is a total of 21 list pages available to choose from.  

Once a name and category are defined, select OK. You will receive a success message after the query is created in Business Central. If the query failed to create, you will be notified with an error message.  

> [!Tip]
> Once the SmartList query is saved, and you return to the list page you initiated SmartList Designer from, you will need to refresh the list page before the new query is available in the navigation.

### Save As

Once edits have been made to an existing SmartList query, the **Save As** action will become available in the context menu (...) in the lower right.  

Use the **Save As** command to save the edits as a new query. Enter a name for your SmartList query. SmartList query names must be unique. If the name entered is not unique, you will receive an error message when you attempt to save the query.  

Select the category to assign your SmartList query to and choose OK.  

### New Query

Another option for creating a query is to start without a data source selected. To create a new query, select the New action from the context (…) menu in the SmartList Designer app.  

> [!Note]
> If you have an existing query definition in progress, you will be prompted to save or discard the changes before continuing.

The first step will be to select a primary data source for your query. Choose the Find Table action. The application will present you with a list of all tables available in  Business Central. Select the table you want to use as your primary data source.

The application auto selects the first 5 fields from the data source selected. From here, the creation of the query is the same as the steps above when the data source was automatically selected for you.

### Assign

If you want to change list page the SmartList query is assigned to, choose the **Assign** action from the context menu **(…)** in the lower right.  

This action will be disabled if you have not yet saved your SmartList query.

## Viewing a SmartList Query

Navigate to the list page that contains the SmartList query you want to render and select the All drop down. Your new SmartList query will appear in the drop down. To render the results, select the SmartList query.  

> [!NOTE]
> A any new SmartList queries created will not be visible until the list page is it associated with has refreshed. A refresh can be done by navigating away from, and back to the list page the SmartList query was associated with or by refreshing Business Central.

### Navigation

Displays custom navigation links created from the **SmartList Management** page. All custom navigation can be pinned to remain open each time the SmartList query is viewed. Custom Navigation will consist of one default custom navigation with additional navigation options. Also see SmartList Management.
Edit a SmartList Query

You may edit any SmartList query that was created using SmartList Designer. To Edit, view the results of the SmartList query from the list page it is associated with.  

Once the results are visible, select the Edit action at the top of the page. SmartList Designer will open with the query definition displayed.

Once changes have been made you may Save the changes, create a new SmartList query by selecting Save As or Cancel and not save any changes.

## SmartList Management

The **SmartList Management** page provides a central location within Business Central to manage the SmartList queries that have been created. By default, only a SUPER user will have permissions to this page. Other users may be granted permissions.  

From the **SmartList Management** page, you have a set of robust actions to help you create new SmartList queries or manage existing SmartList queries.

|Name|Description|
|----|-----------|
|**New**|     Launches SmartList designer without a data source pre-selected.
|**Delete**|    Delete one or more existing SmartList queries.
|**Edit**|    Opens SmartList Designer and visually displays the SmartList query definition.
|**Preview**|    Renders the result set for the SmartList query selected.
|**Export**|    Exports the selected SmartList queries to your downloads folder where they can be imported into another tenant. You must have permissions to export SmartList queries.
|**Import**|    Imports the SmartList query file into your Business Central tenant. You must have permissions to import SmartList queries.
|**Assign Permissions**|    Assign one or more SmartList queries to a user defined permission set.
|**Navigation**|    Create custom navigation to your SmartList query.

The SmartList Management page will provide details related to the SmartList query to assist you in the management of SmartList queries.

|Name|Description|
|----|-----------|
|**Object ID**|    ID that is assigned to a SmartList query created with SmartList Designer. The object range from SmartList queries is 701,000 – 710,000.
|**Name**| This is the name that was defined in SmartList Designer when the SmartList query was created.
|**Description**|    Short description of the SmartList query. By default, the description and name will have the same values.
|**Assigned List Page**|    Displays the list page the SmartList query is assigned to. This will be the query category assignment in SmartList Designer.
|**Primary Table**|    The data source that was defined as the first, or primary source, when the SmartList query was created in SmartList Designer.
|**Last Modified by**| Displays name of user that that modified the SmartList query. If the SmartList query has never been modified, this will be the user that created the SmartList query.
|**Last Modified**|    Display the last date and time the SmartList query was modified. If the SmartList query has never been modified, this will be the date and time the SmartList query was created.

### General Functionality

The SmartList Management page provides general functionality like other list pages in Business Central. You may search, filter, open in Excel, bookmark and create custom views from this list.

The SmartList Manage page contains five default views:

* All
* Finance
* Inventory
* Purchasing
* Sales

SmartList queries that are created will be filtered into one of the views based upon the list (Query Category) they have been assigned to in SmartList Designer. To change the category, select to Edit the SmartList query and reassign using the **Assign** action found in the context menu **(...)** in the lower right portion of the screen.

### Assigning Permissions

SmartList Management makes it easy to assign SmartList queries one at a time or in bulk. Select one or more SmartList queries you want to assign to the same permission set and choose **Assign Permissions**.

The **SmartList Permission Management** page will open and display a list of all user defined permission sets. To assign permissions select one or more permission sets and select OK.

SmartList Permission Management will only add SmartList queries to a permission set(s), it will not allow you to remove or change from one permission set to another. That type of management will need to be from the permissions pages.

Once permissions are granted to a SmartList query, the users with permission will be able to see the SmartList query. However, they may not be able to execute the query if they do not have permissions to the underlying data source(s) referenced in the query definition.

### Export/Import

Use the export/import functionality on the SmartList Management page to share SmartList queries across different tenants.

Select one or more SmartList queries that you would like to export and select export. You will be prompted to provide a file name, or you can keep the default name provided and select OK.

Business Central will package up the SmartList queries you selected and save them to your downloads folder. Only the query definition will be exported and not your data.

Once the SmartList queries have exported, the SmartList Export Results page will appear. The page will list all the SmartList queries that were exported successfully and provide an error message for the SmartList queries that failed to export.

To import, select the Import action, choose the file you want to import and select OK. Once the SmartList queries have imported, the SmartList Import Results page will appear. The page will list all the SmartList queries that were imported successfully and provide an error message for the SmartList queries that failed to import.

> [!Tip]
>A common reason why a SmartList query will fail to import is that a data source found in the query definition does not exist in the tenant the SmartList query is being imported >into. This could happen when a query definition contains an extension data source and the tenant you are importing the query into does not have that same extension installed.

## Custom Navigation

Custom navigation is used to create navigation points to other Business Central pages when rendering a SmartList query. A custom navigation is specific to the SmartList query it was created for.

To view custom navigation, select a SmartList query and the Navigation action at the top of the page. The Navigation List page will open and display any custom navigation that have been created to the selected SmartList query.

### Create Custom Navigation

To create a new custom navigation, follow these steps.

1. Select **Create** at the top of the Navigation list page.
2. Provide a **name** for the custom action you are about to create. This name will be visible when rendering a SmartList query.  
3. Choose a **target page** from the lookup. A target page is the page that you want to navigate to when this SmartList query is viewed.
4. If you want a specific record to be returned on the target page, toggle the **Filter to Record** on. If not, select OK to close the page.
5. Select the **Linking Data Item** from the lookup. This will be the item you want displayed when the target page is opened.
6. Select **OK** to close the page.
7. Repeat these steps to create additional custom navigation.

### Edit Custom Navigation

Select the custom navigation you want to edit, modify the custom navigation, and select OK.

### Delete Custom Navigation

Select the custom navigation you want to delete and select delete.  

### Use as Default

If one or more custom navigation records are created for a given SmartList query, you have the option to choose which one of the actions will be treated as the default navigation. The default action is taken when the hyperlink (underline) field in the SmartList query is selected while the SmartList query data is viewed.

## See also

[Business Intelligence](bi.md)  
