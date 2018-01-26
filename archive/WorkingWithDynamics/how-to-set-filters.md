---
    title: How to Set Filters | Microsoft Docs
    description: You use filters to display certain accounts, customers, entries, or other records by specifying criteria for fields in a table. Only records that match the criteria are displayed. If you specify criteria for multiple fields, then records must match all criteria to be displayed.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Filters
You use filters to display certain accounts, customers, entries, or other records by specifying criteria for fields in a table. Only records that match the criteria are displayed. If you specify criteria for multiple fields, then records must match all criteria to be displayed.  
  
 To improve your filter results, consider the following strategies:  
  
-   Understand where and how filters persist. Filters are window dependent. If you apply a filter on one list and switch to a different list, then the filter is not applied there. The filter persists on the list where you set it until you clear it or specify new criteria.  
  
-   Only enter meaningful filters. For example, you can specify an interval that does not exist and cannot be verified. To enter meaningful filters, you must know the sorting rules that are used.  
  
-   Check your filters by occasionally opening the filter pane. In the Application menu, choose **Customize**, and then choose **Filter Pane** to see an overview of all filters that have been applied. To remove all filters on a page, choose the page title drop-down arrow, and then choose **Clear Filter**. Note that this also cancels a default list view, such as that set for **Sales Orders - Open**.  
  
 The following procedures show the different filtering methods for filtering data that uses the ADD INCLUDE<!--[!INCLUDE[demolong](../../includes/demolong_md.md)]-->.  
  
## Filter to the Value of the Selected Field  
 Instead of typing the filter value into the **Type to filter** field in the filter pane, you can set this filter directly from a line. The filter pane does not have to be visible in the user interface.  
  
#### To filter lines to the value of the selected field  
  
1.  In any page that lists lines, place the pointer in the field that has a value that you want to filter all the lines on.  
  
2.  Right-click the field and then choose **Filter to This Value**.  
  
3.  The visible lines are immediately filtered to those that contain the field value. You can see the value that is being filtered on in the **Type to filter** box.  
  
4.  To remove the applied field filter, press **F3** to move your pointer to the **Type to filter** field. Select and delete the filter value. Press Enter to remove the filter.  
  
## Set a Single Field Filter  
 You can enter the field value and field name in the **Type to filter** field on the filter pane. To view the filter pane, open the Application menu, choose **Customize**, and then choose **Filter Pane**.  
  
 The following procedure describes setting a filter so that only records that have the green location code are displayed.  
  
#### To set a field filter  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
  
2.  In the **Type to filter** box, enter **GREEN**.  
  
3.  Press the Tab key, and in the **Choose a column** drop-down list box, select **Location Code**, for example. You can use choose the field to select the field for the filtering value. Press Enter.  
  
     In the **Customer** list, only records that have **GREEN** as the location code are displayed. You cannot see other records until you remove the filter.  
  
4.  To remove the filter, delete the value in the **Type to filter** field.  
  
     Now you can see all cards in the **Customer** list.  
  
    > [!NOTE]  
    >  The filter fields that are available in the drop-down list box are the same as those that are visible as columns on the page. You can personalize this by choosing columns. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  
  
 If you want to set multiple field filters, you must use the Advanced Filter function, which is described in the following procedure.  
  
## Set Multiple Field Filters  
 If you want to filter on more than one field, then you must use the Advanced Filter function on the filter pane. The following example uses the **Chart of Accounts.**  
  
#### To set a filter for multiple fields  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
  
2.  Select the page title menu, and then choose **Advanced filter**.  
  
     A new filter pane that displays advanced search criteria opens.  
  
3.  On the first line for the **Where** filter, in the **No.** column, choose the field, and then choose **Account Type**.  
  
4.  In the **Enter a value** field, choose the drop-down arrow.  
  
5.  Select the **Total** check box. Only lines with account type **Total** are displayed.  
  
     You can filter the data more by specifying more criteria.  
  
6.  Choose **Add Filter** to start a new line.  
  
7.  In the **And** field, select **Balance**.  
  
8.  In the **Enter a value** field, enter **> 10000**. All lines with balances that are greater than 10,000 are displayed.  
  
     You can continue adding new filters or modifying existing criteria.  
  
9. To clear a filter, choose the **Delete X** to clear the filter line that you no longer need.  
  
10. To clear all filters, select the **Chart of Accounts** page title menu, and then choose **Clear Filter**.  
  
    > [!NOTE]  
    >  The filter fields that are available in the drop-down list box are the same as those that are visible as columns on the page. You can personalize this by choosing columns.  
  
## Set a Filter in a Calculated Field  
 A FlowFilter filters the contents of the fields that display amounts or quantities that are calculated from entries in other tables. For example, you can use a FlowFilter to see entries in other tables, such as those entries with a certain date interval or with a particular location code. You can enter FlowFilters in fields that end with the term Filter, such as **Date Filter**, **Global Dimension 1 Filter**, or **Location Filter**. For more information, see [FlowFilters](../FullExperience/flowfilters.md).  
  
> [!NOTE]  
>  FlowFilters also exist on report and batch job request pages along-side normal field filters. Beware that the two types of filters cannot always be combined on reports and batch jobs as you may think.  
>   
>  For example, if you set a Currency Code field filter in the **Show Results** group on the **Adjust Exchange Rate** batch job and you also set a Customer FlowFilter in the **Limit totals to** group, then the batch job will not adjust only the filtered currencies for the filtered customers. The reason is that the batch job in question is based on the **Currency** table, not on the **Customer** table.  
  
 You use FlowFilters in different ways, depending on whether it is used on a card, a list, or a report. The following examples use the item card and the chart of accounts.  
  
#### To set a FlowFilter on a card  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
  
2.  Select the page title menu again, and then choose **Limit totals**.  
  
3.  A **Limit totals To** section is displayed on the filter pane.  
  
4.  In the **Where** field, in the **No.** column, choose the field, and then choose **Location Filter**.  
  
5.  Choose the **Enter a value** field.  
  
6.  Select the **GREEN** location. The location that you selected is displayed in the **Limit totals To** section.  
  
7.  Select an item in the list, for example, item 1900-S. On the **Home** tab, in the **Manage** group, choose **Edit** to open the **Item** card.  
  
     The window shows the various availability quantities on the **General** FastTab for the GREEN location only.  
  
8.  To remove the filter, on the **Actions** tab, in the **Page** group, choose **Clear Filter**.  
  
#### To set a FlowFilter on a list page  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
  
2.  Select the page title menu, and then choose **Limit Totals**.  
  
     A **Limit totals To** section is displayed on the filter pane.  
  
3.  On the first line, in the **Where** field, in the **No.** column, choose the field, and then choose **Department Filter**.  
  
4.  Choose the **Enter a value** field.  
  
5.  Select **Sales**. The department that you selected is displayed in the **Limit Totals To** filter.  
  
 When you have finished viewing your data with FlowFilters, you can choose **Delete X** on the line to clear the filter.  
  
## See Also  
 [Enter Criteria in Filters](../FullExperience/enter-criteria-in-filters.md)   
 [FlowFilters](../FullExperience/flowfilters.md)   
 [Sorting](../FullExperience/sorting.md)   
 [Working with Product Name](../FullExperience/working-with-$-p_1-product-name-$-.md)   
 [Keyboard Shortcuts](../FullExperience/keyboard-shortcuts.md)