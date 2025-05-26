---
title: Work with dimensions to track and analyze data
description: Use dimensions to categorize entries, such as by department or project, so you can more easily track and analyze data to help you make good business decisions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 08/08/2024
ms.custom: bap-template
ms.search.keywords: analysis, history, track, business intelligence
ms.search.form: 118, 408, 479, 480, 481, 484, 536, 537, 538, 539, 540, 541, 542, 543, 544, 545, 548, 560, 562, 564, 567, 568, 577, 578, 580, 699, 1343, 2580, 2581, 2582, 2583, 2584, 2585, 2586, 2587, 2588, 2590, 2591, 2592, 2593, 9083, 9233, 9251, 9252, 9253
---

# Work with dimensions

Dimensions are values that categorize entries so you can track and analyze them on documents, such as sales orders. Dimensions can, for example, indicate the project or department an entry came from.  

So, instead of setting up separate general ledger accounts for each department and project, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts. Learn more at [Business Intelligence](bi.md).

Another example is to set up a dimension called *Department*, then use that dimension when you post sales documents. This way, you can use business intelligence tools to see which department sold which items. The more dimensions you use, the more detailed are the reports you base your business decisions on. In fact, a single sales entry can include information from multiple dimensions, such as:  

* The account the item sale was posted to.  
* Where the item was sold.
* Who sold it.
* Which customer bought it.

## Analyze by dimensions

Dimensions play an important role in business intelligence, such as when defining analysis views. Learn more at [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

> [!TIP]
> A quick way to analyze transactional data by dimensions is to use the **Set Dimension Filter** action to filter totals by dimensions in the chart of accounts and on pages for entries.

> [!NOTE]
> Analysis views often use data from dimensions. If you discover an incorrect dimension has been used on posted general ledger (G/L) entries, you can correct the dimension values and update your analysis views. This helps keep your financial reports and analyses accurate. Learn more at [Troubleshooting and Correcting Dimensions](finance-troubleshooting-correcting-dimensions.md#changing-dimension-assignments-after-posting).

## Dimension sets

A dimension set is a unique combination of dimension values. They're stored as dimension set entries in the database. Each dimension set entry represents a single dimension value. In addition, each dimension set, and dimension set entry within it, is identified by a common dimension set ID.  

When you create a journal line, document header, or document line, you can specify a combination of dimension values. Instead of explicitly storing each dimension value in the database, a dimension set ID is assigned to the journal line, document header, or document line to specify the dimension set.  

## Set up dimensions

You can define dimensions and dimension values to categorize journals and documents, such as sales orders and purchase orders. You set up dimensions on the **Dimensions** page, where you create one line for each dimension, such as *Project*, *Department*, *Area*, and *Salesperson*.

You also set up values for dimensions. Let's say values represent your company's departments. Dimension values can be set up in a hierarchical structure similar to the chart of accounts. That means data can be broken down into various levels of granularity, and subsets of dimension values can be totaled. You can define as many dimensions and dimension values as you need, and everyone in your company can use them.

When dimensions and values are set up, you can define global and shortcut dimensions on the **General Ledger Setup** page. These dimensions are then always available for you to select as fields on journal and document lines, and ledger entries, without opening the **Dimensions** page first. Learn more in the [To set up global and shortcut dimensions](finance-dimensions.md#to-set-up-global-and-shortcut-dimensions) section.

* **Global Dimensions** are used as filters, for example, on reports, batch jobs, and XMLports. You can use only two global dimensions, so choose dimensions you'll use often.
* **Shortcut Dimensions** are available as fields on journals, document lines, and ledger entries. You can create up to eight of these.  

> [!NOTE]
> After you use a new dimension in any entry, such as a line or new record, you cannot delete the dimension, even if you do not post the entry. This is because [!INCLUDE[prod_short](includes/prod_short.md)] immediately creates a dimension set for the line or record. Learn more in the [Dimension Sets](finance-dimensions.md#dimension-sets) section.

### To set up default dimensions for customers, vendors, and other accounts

You can assign a default dimension for a specific account. The dimension is copied to the journal or document when you enter the account number on a line, but you can delete or change the code on the line if appropriate. You can also require a dimension for posting an entry in a specific type of account. > 

> [!NOTE]
> Default dimension priorities open up for scenarios in sales and purchases that you might want to pay special attention to. When you use default dimension priorities on sales and purchase documents, [!INCLUDE [prod_short](includes/prod_short.md)] always considers the dimensions in the header as coming from the customer or vendor. This is true for dimensions that you set manually or by default, and is especially relevant when you use default dimensions on locations and items but not on customers or vendors.
>
> **Example**
>
> You have a scenario with the following dimension settings:
>
> * A customer without default dimensions
> * An item with ADM as the dimension value for the DEPARTMENT dimension
> * A location with PROD as the dimension value the DEPARTMENT dimension
> * Default dimension priorities are set as Customer > Item > Location
>
> When you create a new document in this scenario, dimensions are used as follows:
>
> * If you create a new document and add a location, the default value for new lines will be PROD. When you add lines with items, [!INCLUDE [prod_short](includes/prod_short.md)] will keep PROD because it comes from the header of the document.
>
> * If you create a new document and add items that have the ADM dimension value, and then specify a location in the header of the document, [!INCLUDE [prod_short](includes/prod_short.md)] will ask whether you want to overwrite the existing lines because there's a conflict.
>
> We recommend that you to test your default dimensions setup, dimension priorities, and the order in which you enter data in documents.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions**, then choose the related link.  
2. On the **Dimensions** page, select the relevant dimension, then choose the **Account Type Default Dim** action.  
3. Fill in a line for each new default dimension you want to set up. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]  
> If you want to require a dimension but don't want to assign a default value to the dimension, leave the **Dimension Value Code** field blank, then select **Code Mandatory** in the **Value Posting** field.  

> [!WARNING]  
> If an account is used in an **Adjust Exchange Rates** or **Post Inventory Cost to G/L** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  

> [!NOTE]  
> If an account must have a different dimension than the default dimension assigned to the account type, you must set up a new default dimension for the account. The default dimension for the account then replaces the default dimension for the account type.  

### To set up default dimension priorities

Different account types, such as a customer account and an item account, can have different default dimensions. As a result, an entry might have more than one  proposed default dimension. To avoid such conflicts, you can apply priority rules to the different sources.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Default Dimension Priorities**, then choose the related link.  
2. On the **Default Dimension Priorities** page, in the **Source Code** field, enter the source code for the entry table to which the default dimension priorities will apply.  
3. Fill in a line for each default dimension priority you want for the selected source code.
4. Repeat the procedure for each source code you want to set up default dimension priorities for.  

> [!IMPORTANT]  
> If you set up two tables with the same priority for the same source code, [!INCLUDE[prod_short](includes/prod_short.md)] always selects the table with the lowest table ID.  

### To set up dimension combinations

To avoid posting entries with contradictory or irrelevant dimensions, you can block or limit specific combinations of two dimensions. A blocked dimension combination means you can't post both dimensions on the same entry regardless of what the dimension values are. In contrast, a limited dimension combination means you can post both dimensions to the same entry, but only for certain combinations of dimension values.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimension Combinations**, and then choose the related link.  
2. On the **Dimension Combinations** page, choose the dimension combination field you want from the following options.  

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**No limitation**|This dimension combination has no restrictions. All dimensions values are allowed.|  
    |**Limited**|This dimension combination has restrictions depending on which dimension values that you enter. You must define the limitations on the **Dimension Value Combination** page.|  
    |**Blocked**|This dimension combination isn't allowed.|  

3. If you selected the **Limited** option, you must define which combinations of dimension values are blocked. To do this, choose the field to define the dimension value combination.  
4. Now select a dimension value combination that is blocked and enter **Blocked** in the field. A blank field means the dimension value combination is allowed. Repeat if multiple combinations are blocked.  

> [!NOTE]  
> The same dimensions are displayed in both rows and columns, meaning all dimension combinations appear two times. [!INCLUDE[prod_short](includes/prod_short.md)] automatically displays the setting in both fields. You cannot select anything in the fields from the upper-left corner and down, because those fields have the same dimension in both rows and columns.  
>
> The selected option is not visible before you exit the field.  
>
> To show the name of the dimensions instead of the code, select the **Show Column Name** field.

### To set up global and shortcut dimensions

Global and shortcut dimensions can be used as filters in [!INCLUDE[prod_short](includes/prod_short.md)], including on reports, batch jobs, ledger entry pages, and analysis views. Global and shortcut dimensions can be inserted directly without first opening the **Dimensions** page. On journal and document lines, you can select global and shortcut dimensions in a field on the line. You can set up two global dimensions and eight shortcut dimensions. Choose the dimensions that you use most frequently.

> [!IMPORTANT]
> Changing a global or shortcut dimension requires all entries posted with the dimension be updated. To change a global dimension, you can use the **Change Global Dimensions** function, but that can be time-consuming, may affect performance, and tables may be locked during the update. Make sure you choose your global and shortcut dimensions carefully so you won't have to change them later. To change a shortcut dimension, use the **Change Dimensions** action.
>
> Learn more in the [To change global dimensions](finance-dimensions.md#to-change-global-dimensions) section.

> [!NOTE]
> When you add or change a global or shortcut dimension, you are automatically signed out and back in so the new value is prepared for use.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, then choose the related link.
2. On the **Dimensions** FastTab, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### To change global dimensions

When you change a global or shortcut dimension, all entries posted with that dimension are updated. Because this process may be time-consuming and can affect performance, two different modes are provided to adapt the process to the size of the database.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. Choose the **Change Global Dimensions** action.
3. At the top of the page, select one of the following two modes for running the batch job.

    |Option|Description|
    |-|-|
    |**Sequential**|(Default) The change is done in one transaction that reverts all entries to the dimensions they had before the change.<br /><br />This option is recommended if the company has relatively few posted entries, in which case the batch job takes the shortest time to complete. The process locks multiple tables and blocks other users until it's done. Note that with large databases, the process might not complete in this mode. In that case, use the **Parallel** option.|
    |**Parallel**|The dimension change happens in multiple background sessions and the operation is split into multiple transactions. To use this option, turn on the **Parallel Processing** toggle. <br /><br />We recommended this option for large databases or companies with numerous posted entries because it will complete in the shortest time. Note that in this mode, the update process won't start if there's more than one active database session.|  

4. In the **Global Dimension 1 Code** and/or **Global Dimension 2 Code** fields, enter the new dimension(s). The current dimensions are displayed in gray behind the fields.
5. Depending on the mode, do one of the following:
    * In **Sequential** mode, choose the **Start** action.
    * In **Parallel** mode, choose the **Prepare** action.

    The **Log Entries** tab is filled with information about the dimensions to be changed.
6. Sign out of [!INCLUDE[prod_short](includes/prod_short.md)], then sign in again.
7. Choose the **Start** action to begin the parallel processing of the dimension changes.

### Example of dimension setup

Let's say your company wants to track transactions based on organizational structure and geographic locations. To do that, you set up two dimensions on the **Dimensions** page:

* **AREA**  
* **DEPARTMENT**  

| Code | Name | Code Caption | Filter Caption |
| --- | --- | --- | --- |
| AREA |Area |Area Code |Area Filter |
| DEPARTMENT |Department |Department Code |Department Filter |

For **AREA**, add the following dimension values:

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

For the two main geographic areas, Americas and Europe, you add subcategories for regions by indenting the dimension values. This lets you report on sales or expenses in regions, and get totals for the larger geographic areas. You could also choose to use countries, regions, counties, or cities as your dimension values, depending on your business.

> [!NOTE]  
> To set up a hierarchy, the codes must be in alphabetical order. This includes the codes of the dimension values provided in [!INCLUDE[prod_short](includes/prod_short.md)].  

For **DEPARTMENT**, add the following dimension values:

| Code | Name | Dimension Value Type |
| --- | --- | --- |
| ADMIN |Administration |Standard |
| PROD |Production |Standard |
| SALES |Sales |Standard |

With this setup, you can add your two dimensions as the two global dimensions on the **General Ledger Setup** page. This means you can use AREA and DEPARTMENT as filters for general ledger entries, as well as on all reports. Both global dimensions are also automatically available for use on entry lines and document headers as shortcut dimensions.

## Getting an overview of dimensions used multiple times

The **Default Dimensions-Multiple** page specifies how a group of accounts uses dimensions and dimension values. You can set this up by highlighting multiple accounts, then specifying default dimensions and dimension values for them. After that, the application suggests these dimensions and dimension values whenever one of these accounts is used, such as on a journal line. This makes entry posting easier for the user, as the dimension fields are filled in automatically. Also note, however, that the dimension values suggested can be changed on, for example, a journal line.

The **Default Dimensions-Multiple** page contains the following fields:

|Field|Description|
|-----|-----------|  
|**Dimension Code**|Shows all dimensions defined as default dimensions on one or more highlighted accounts. By choosing this field, you can see a list of all available dimensions. If you select a dimension, that dimension is defined as a default dimension for all highlighted accounts.|
|**Dimension Value Code**|Shows either a single dimension value or the term (Conflict). If a dimension value is shown in the field, then all highlighted accounts have the same default dimension value for a dimension. If the term (Conflict) is shown in the field, then not all highlighted accounts have the same default dimension value for a dimension. Upon choosing the **Dimension Code** field, you'll see a list of all available dimension values for a dimension. If you select a dimension value, it will be defined as a default dimension value for all highlighted accounts.|
|**Value Posting**|Shows either a single value posting rule or the term (Conflict). If a value posting rule is shown in the field, then all highlighted accounts have the same value posting rule for a dimension value. If the term (Conflict) is shown in the field, then not all the highlighted accounts have the same value posting rule for a dimension value. Upon choosing the **Value Posting** field, you'll see a list of value posting rules for a dimension. If you select a value posting rule, it will be applied to all highlighted accounts.|

## Use dimensions

In a document such as a sales order, you can add dimension information for both an individual document line and the document itself. So on the **Sales Order** page, you could enter dimension values for the first two shortcut dimensions on the individual sales lines, then add more dimension information if you choose the **Dimensions** button.  

If you work in a journal instead, you can add dimension information to an entry in the same way, if you have set up shortcut dimensions as fields directly on journal lines.  

You can also set up default dimensions for accounts or account types, so dimensions and dimension values are filled in automatically.

### To view global dimensions in ledger entry pages

Global dimensions are always company-defined and company-named. To see the global dimensions for your company, open the **General Ledger Setup** page.

In a ledger entry page, you can see whether there are global dimensions for the entries. The two global dimensions differ from your other dimensions because you can use them as filters anywhere in [!INCLUDE[prod_short](includes/prod_short.md)].  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**,  then choose the related link.  
2. On the **Chart of Accounts** page, choose the **Ledger Entries** action.  
3. To see only entries that are relevant, set one or more filters on the page.  
4. To see all the dimensions for an entry, select the entry, then choose the **Dimensions** action.  

> [!NOTE]  
> The **Ledger Entry Dimensions** page displays the dimensions one ledger entry at a time. You'll see as you scroll through the ledger entries, the content on the **Ledger Entry Dimensions** page changes accordingly.

## Related information

[Business Intelligence](bi.md)    
[Finance](finance.md)    
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
