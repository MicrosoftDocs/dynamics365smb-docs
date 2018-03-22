---
title: Work with Dimensions| Microsoft Docs
description: You use dimensions to categorize entries, for example, by department or project, so you can easily track and analyze data.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.date: 01/25/2018
ms.author: sgroespe

---
# Working with Dimensions
To make it simpler to perform analysis on documents such as sales orders, you can use dimensions. Dimensions are attributes and values that categorize entries so you can track and analyze them. For example, dimensions can indicate the project or department an entry came from.  

For example, instead of setting up separate general ledger accounts for each department and project, you can use dimensions. This gives a rich opportunity for analysis, without creating a complicated chart of accounts. For more information, see [Business Intelligence](bi.md).

Another example is to set up a dimension called *Department*, and use this dimension when you post sales documents. This will let you use business intelligence tools to see which department sold which items.
The more dimensions you use, the more detailed reports you can base your business decisions on. For example, a single sales entry can include multiple dimension information, such as:  

* The account the item sale was posted to  
* Where the item was sold
* Who sold it
* The kind of customer who bought it  

## Analyzing by Dimensions
The Dimensions functionality plays an important role in business intelligence, such as when defining analysis views. For more information, see [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

> [!TIP]
> As a quick way to analyze transactional data by dimensions, you can filter totals in the chart of accounts and entries in all **Entries** windows by dimensions. Look for the **Set Dimension Filter** action.

## Dimension Sets
A dimension set is a unique combination of dimension values. It is stored as dimension set entries in the database. Each dimension set entry represents a single dimension value. The dimension set is identified by a common dimension set ID that is assigned to each dimension set entry that belongs to the dimension set.  

When you create a journal line, document header, or document line, you can specify a combination of dimension values. Instead of explicitly storing each dimension value in the database, a dimension set ID is assigned to the journal line, document header, or document line to specify the dimension set.  

## Setting Up Dimensions
You can define the dimensions and dimension values to categorize journals and documents, such as sales orders and purchase orders. You set up dimensions in the **Dimensions** window, where you create one line for each dimension, such as *Project*, *Department*, *Area*, and *Salesperson*.

You also set up values for dimensions. For example, values might be departments in your company. Dimension values can be set up in a hierarchical structure similar to the chart of accounts, so that data can be broken down into various levels of granularity, and subsets of dimension values can be totaled. You can define as many dimensions and dimension values as you need, and everyone in your company can use them.

You can also set up some global and shortcut dimensions:  

* **Global dimensions** are used as filters, for example, on reports and batch jobs. You can use only two global dimensions, so choose dimensions you will use often.
* **Shortcut dimensions** are available as fields on journal and document lines. You can create up to six of these.  

### Setting Up Default Dimensions for Customers, Vendors, and Other accounts
You can assign a default dimension for a specific account. The dimension will be copied to the journal or document when you enter the account number on a line, but you can delete or change the code on the line if appropriate. You can also make a dimension required for posting an entry with a specific type of account.  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dimensions**, and then choose the related link.  
2.  In the **Dimensions** window, select the relevant dimension, and then choose the **Account Type Default Dim** action.  
4.  Fill in a line for each new default dimension that you want to set up. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]  
>  If you want to make a dimension required but you do not want to assign a default value to the dimension, leave the **Dimension Value Code** field blank and then select **Code Mandatory** in the **Value Posting** field.  

> [!WARNING]  
>  If an account is used in the **Adjust Exchange Rates** batch job or the **Post Inventory Cost to G/L** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  

> [!NOTE]  
>  If an account must have a different dimension assigned to it than the default dimension already set up for the account type, you must set up a default dimension for this account. The default dimension for the individual account then replaces the default dimension for the account type.  

### To set up default dimension priorities  
Different account types, such as a customer account and an item account, can have different default dimensions set up. As a result, an entry can have more than one default dimension proposed for a dimension. To avoid such conflicts, you can apply priority rules to the different sources.  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Default Dimension Priorities**, and then choose the related link.  
2.  In the **Default Dimension Priorities** window, in the **Source Code** field, enter the source code for the entry table to which default dimension priorities will apply.  
3.  Fill in a line for each default dimension priority that you want for the selected source code.
4.  Repeat the procedure for each source code for which you want to set up default dimension priorities.  

> [!IMPORTANT]  
>  If you set up two tables with the same priority for the same source code, [!INCLUDE[d365fin](includes/d365fin_md.md)] will always select the table with the lowest table ID.  

### To set up dimension combinations  
To avoid posting entries with contradictory or irrelevant dimensions, you can block or limit specific combinations of two dimensions. A blocked dimension combination means that you cannot post both dimensions on the same entry regardless of what the dimension values are. A limited dimension combination lets you post both dimensions to the same entry, but only for certain combinations of dimension values.

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Dimension Combinations**, and then choose the related link.  
2.  In the **Dimension Combinations** window, choose the field of the dimension combination and select one of the following options.  

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**No limitation**|This dimension combination has no restrictions. All dimensions values are allowed.|  
    |**Limited**|This dimension combination has restrictions depending on which dimension values that you enter. You must define the limitations in the **Dimension Value Combination** window.|  
    |**Blocked**|This dimension combination is not allowed.|  

3.  If you selected the **Limited** option, you must define which combinations of dimension values are blocked. To do this, choose the field to define the dimension combination.  
4.  Now select a dimension value combination that is blocked and enter **Blocked** in the field. A blank field means that the dimension value combination is allowed. Repeat if multiple combinations are blocked.  

> [!NOTE]  
>  The same dimensions are displayed in both rows and columns and, therefore, all dimension combinations appear two times. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically displays the setting in both fields. You cannot select anything in the fields from the upper-left corner and down, because these fields have the same dimension in both rows and columns.  
>   
>  The selected option is not visible before you exit the field.  
>   
>  To show the name of the dimensions instead of the code, select the **Show Column Name** field.

### Getting an Overview of Dimensions used Multiple Times
The **Default Dimensions-Multiple** window specifies how a group of accounts use dimensions and dimension values. You can do this by highlighting multiple accounts and then specifying default dimensions and dimension values for all the accounts you have highlighted in the account list. When you specify default dimensions for the highlighted accounts, the program will suggest these dimensions and dimension values whenever one of these accounts is used, for example on a journal line. This makes entry posting easier for the user, as the dimension fields are filled in automatically. However, the dimension values that are suggested can be changed on, for example, a journal line.

The **Default Dimensions-Multiple** window contains the following fields:
|Field|Description|
|----------------------------------|---------------------------------------|  
|**Dimension Code**|Shows all dimensions that have been defined as default dimensions on one or more of the highlighted accounts. By choosing the field, you can see a list of all available dimensions. If you select a dimension, the selected dimension will be defined as a default dimension for all highlighted accounts.|
|**Dimension Value Code**|Shows either a single dimension value or the term (Conflict). If a dimension value is shown in the field, then all highlighted accounts have the same default dimension value for a dimension. If the term (Conflict) is shown in the field, then not all of the highlighted accounts have the same default dimension value for a dimension. By choosing the field, you can see a list of all available dimension values for a dimension. If you select a dimension value, the selected dimension value will be defined as a default dimension value for all highlighted accounts.|
|**Value Posting**|Shows either a single value posting rule or the term (Conflict). If a value posting rule is shown in the field, then all highlighted accounts have the same value posting rule for a dimension value. If the term (Conflict) is shown in the field, then not all of the highlighted accounts have the same value posting rule for a dimension value. By choosing the Value Posting field, you can see a list of value posting rules. If you select a value posting rule, it will be applied for all highlighted accounts.|

### Example of Dimension Setup
Let's say that your company wants to track transactions based on organizational structure and geographic locations. To do that, you can set up two dimensions in the **Dimensions** window:

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
>   To set up a hierarchy, the codes must be in alphabetical order. This includes the codes of the dimension values that are provided in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

For **DEPARTMENT**, you add the following dimension values:

| Code | Name | Dimension Value Type |
| --- | --- | --- |
| ADMIN |Administration |Standard |
| PROD |Production |Standard |
| SALES |Sales |Standard |

With this set up, you then add your two dimensions as the two global dimensions in the **General Ledger Setup** window. This means that you can use AREA and DEPARTMENT as filters for general ledger entries, as well as on all reports and account schedules. Both global dimensions are also automatically available for use on entry lines and document headers as shortcut dimensions.  

## Using Dimensions
In a document such as a sales order, you can add dimension information for both an individual document line and the document itself. For example, in the **Sales Order** window, you can enter dimension values for the first two shortcut dimensions on the individual sales lines, and you can add more dimension information if you choose the **Dimensions** button.  

If you work in a journal instead, you can add dimension information to an entry in the same way, if you have set up shortcut dimensions as fields directly on journal lines.  

You can set up default dimensions for accounts or account types, so that dimensions and dimension values are filled in automatically.

## To view global dimensions in ledger entry windows  
Global dimensions are always company\-defined and company-named. To see the global dimensions for your company, open the **General Ledger Setup** window.  

In a ledger entry window, you can see whether there are global dimensions for the entries. The two global dimensions differ from the rest of your dimensions because you can use them as filters anywhere in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  In the **Chart of Accounts** window, choose the **Ledger Entries** action.  
3.  To see only the entries that are relevant, set one or more filters on the window.  
4.  To see all the dimensions for an entry, select the entry, and then choose the **Dimensions** action.  

> [!NOTE]  
>  The **Ledger Entry Dimensions** window displays the dimensions for one ledger entry at a time. As you scroll through the ledger entries, the content in the **Ledger Entry Dimensions** window changes accordingly.  

## See Also
[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
