---
title: Set Up Dimensions
description: Learn how to set up dimensions to categorize entries, for example, by department or project, so you can easily track and analyze data.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: analysis, history, track
ms.author: edupont
ms.date: 10/01/2020
---
# Setting Up Dimensions

You can define the dimensions and dimension values to categorize journals and documents, such as sales orders and purchase orders. You set up dimensions on the **Dimensions** page, where you create one line for each dimension, such as *Project*, *Department*, *Area*, and *Salesperson*.

You also set up values for dimensions. For example, values might be departments in your company. Dimension values can be set up in a hierarchical structure similar to the chart of accounts, so that data can be broken down into various levels of granularity, and subsets of dimension values can be totaled. You can define as many dimensions and dimension values as you need, and everyone in your company can use them.

When dimensions and values are set up, you can define global and shortcut dimensions on the **General Ledger Setup** page that will always be available to select as fields on journal and document lines, and ledger entries, without having to open the **Dimensions** page first. For more information, see the [To set up global and shortcut dimensions](#to-set-up-global-and-shortcut-dimensions) section.

* **Global Dimensions** are used as filters, for example, on reports, batch jobs, and XMLports. You can use only two global dimensions, so choose dimensions you will use often.
* **Shortcut Dimensions** are available as fields on journals, document lines, and ledger entries. You can create up to eight of these.  

## Default dimensions for customers, vendors, and other accounts

You can assign a default dimension for a specific account. The dimension will be copied to the journal or document when you enter the account number on a line, but you can delete or change the code on the line if appropriate. You can also make a dimension required for posting an entry with a specific type of account.  

### To set up default dimensions for customers, vendors, and other accounts

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions**, and then choose the related link.  
2. On the **Dimensions** page, select the relevant dimension, and then choose the **Account Type Default Dim** action.  
3. Fill in a line for each new default dimension that you want to set up. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]  
> If you want to make a dimension required but you do not want to assign a default value to the dimension, leave the **Dimension Value Code** field blank and then select **Code Mandatory** in the **Value Posting** field.  

> [!WARNING]  
> If an account is used in the **Adjust Exchange Rates** batch job or the **Post Inventory Cost to G/L** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  

> [!NOTE]  
> If an account must have a different dimension than the default dimension for the account type, you must set up a default dimension for this account. The default dimension for the account then replaces the default dimension for the account type.  

## Default dimension priorities

Different account types, such as a customer account and an item account, can have different default dimensions set up. As a result, an entry can have more than one default dimension proposed for a dimension. To avoid such conflicts, you can apply priority rules to the different sources.  

### To set up default dimension priorities

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Default Dimension Priorities**, and then choose the related link.  
2. On the **Default Dimension Priorities** page, in the **Source Code** field, enter the source code for the entry table to which default dimension priorities will apply.  
3. Fill in a line for each default dimension priority that you want for the selected source code.
4. Repeat the procedure for each source code for which you want to set up default dimension priorities.  

> [!IMPORTANT]  
> If you set up two tables with the same priority for the same source code, [!INCLUDE[prod_short](includes/prod_short.md)] will always select the table with the lowest table ID.  

## Dimension combinations

To avoid posting entries with contradictory or irrelevant dimensions, you can block or limit specific combinations of two dimensions. A blocked dimension combination means that you cannot post both dimensions on the same entry regardless of what the dimension values are. A limited dimension combination lets you post both dimensions to the same entry, but only for certain combinations of dimension values.

### To set up dimension combinations

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimension Combinations**, and then choose the related link.  
2. On the **Dimension Combinations** page, choose the field of the dimension combination and select one of the following options.  

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**No limitation**|This dimension combination has no restrictions. All dimensions values are allowed.|  
    |**Limited**|This dimension combination has restrictions depending on which dimension values that you enter. You must define the limitations on the **Dimension Value Combination** page.|  
    |**Blocked**|This dimension combination is not allowed.|  

3. If you selected the **Limited** option, you must define which combinations of dimension values are blocked. To do this, choose the field to define the dimension combination.  
4. Now select a dimension value combination that is blocked and enter **Blocked** in the field. A blank field means that the dimension value combination is allowed. Repeat if multiple combinations are blocked.  

> [!NOTE]  
> The same dimensions are displayed in both rows and columns and, therefore, all dimension combinations appear two times. [!INCLUDE[prod_short](includes/prod_short.md)] automatically displays the setting in both fields. You cannot select anything in the fields from the upper-left corner and down, because these fields have the same dimension in both rows and columns.  
>
> The selected option is not visible before you exit the field.  
>
> To show the name of the dimensions instead of the code, select the **Show Column Name** field.

### Global and shortcut dimensions

Global and shortcut dimensions can be used as filters in [!INCLUDE[prod_short](includes/prod_short.md)], including on reports, batch jobs, ledger entry pages, and analysis views. Global and shortcut dimensions are always available to be inserted directly without first opening the **Dimensions** page. On journal and document lines, you can select global and shortcut dimensions in a field on the line. You can set up two global dimensions and eight shortcut dimensions. Choose the dimensions that you use most frequently.

> [!Important]  
> Changing a global or shortcut dimension requires that all entries posted with the dimension are updated. To change a global dimension, use the **Change Global Dimensions** function, but it can be time-consuming and may affect performance and tables may be locked during the update. Therefore, choose your global and shortcut dimensions carefully so that you do not have to change them later. To change a shortcut dimension, use the **Change Dimensions** action.
>
> For more information, see the [To change global dimensions](#to-change-global-dimensions) section.

> [!Note]
> When you add or change a global or shortcut dimension, you are automatically signed out and back in so that the new value is prepared for use.

### To set up global and shortcut dimensions

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. On the **Dimensions** FastTab, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### To change global dimensions

When you change a global or shortcut dimension, all entries posted with the dimension in question are updated. Because this process may be time-consuming and can affect performance, two different modes are provided to adapt the process to the size of the database.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. Choose the **Change Global Dimensions** action.
3. At the top of the page, select one of the following options to define in which mode the batch job is run.

    |Option|Description|
    |-|-|
    |**Sequential**|(Default) The change is done in one transaction that reverts all entries to the dimensions they had before the change.<br /><br />This option is recommended if the company contains relatively few posted entries where it will take the shortest time to complete. The process locks multiple tables and blocks other users until it is done. Note that on large databases, the process may not be able to complete in this mode. In that case, use the **Parallel** option.|
    |**Parallel**|The dimension change happens in multiple background sessions and the operation is split into multiple transactions. To use this option, turn on the **Parallel Processing** toggle. <br /><br />We recommended this option for large databases or companies with many posted entries because it will take the shortest time to complete. Note that with this mode, the update process will not start if there are more than one active database sessions.|  

4. In the **Global Dimension 1 Code** and/or **Global Dimension 2 Code** fields, enter the new dimension(s). The current dimensions are displayed in gray behind the fields.
5. Depending on the mode, do one of the following:
    * In **Sequential** mode, choose the **Start** action.
    * In **Parallel** mode, choose the **Prepare** action.

    The **Log Entries** tab is filled with information about the dimensions that will be changed.
7. Sign out of [!INCLUDE[prod_short](includes/prod_short.md)], and then sign in again.
8. Choose the **Start** action to start the parallel processing of the dimension changes. <!--is this also dependent on the mode?-->

## Example of Dimension Setup

Let's say that your company wants to track transactions based on organizational structure and geographic locations. To do that, you can set up two dimensions on the **Dimensions** page:

* **AREA**  
* **DEPARTMENT**  

| Code | Name | Code Caption | Filter Caption |
| --- | --- | --- | --- |
| AREA |Area |Area Code |Area Filter |
| DEPARTMENT |Department |Department Code |Department Filter |

For **AREA**, you add the following dimension values:

| Code | Name | Dimension Value Type |
| --- | --- | --- |
| 10 |Americas |Begin-Total |
| 20 |North America |Standard |
| 30 |Pacific |Standard |
| 40 |South America |Standard |
| 50 |Americas, Total |End-Total |
| 60 |Europe |Begin-Total |
| 70 |EU |Standard |
| 80 |Non-EU |Standard |
| 90 |Europe, Total |End-Total |

For the two main geographic areas, Americas and Europe, you add subcategories for regions by indenting the dimension values. This will let you report on sales or expenses in regions, and get totals for the larger geographic areas. You could also choose to use countries or regions as your dimension values, or counties or cities, depending on your business.

> [!NOTE]  
> To set up a hierarchy, the codes must be in alphabetical order. This includes the codes of the dimension values that are provided in [!INCLUDE[prod_short](includes/prod_short.md)].  

For **DEPARTMENT**, you add the following dimension values:

| Code | Name | Dimension Value Type |
| --- | --- | --- |
| ADMIN |Administration |Standard |
| PROD |Production |Standard |
| SALES |Sales |Standard |

With this set up, you can add your two dimensions as the two global dimensions on the **General Ledger Setup** page. This means that you can use AREA and DEPARTMENT as filters for general ledger entries, as well as on all reports and account schedules. Both global dimensions are also automatically available for use on entry lines and document headers as shortcut dimensions.

## See Related Training at [Microsoft Learn](/learn/modules/dimensions-dynamics-365-business-central/index)

## See Also

[Working with Dimensions](finance-dimensions.md)  
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)  
[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
