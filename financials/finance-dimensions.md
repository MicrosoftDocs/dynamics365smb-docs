---
title: Work with Dimensions| Microsoft Docs
description: You use dimensions to categorize entries, for example, by department or project, so you can easily track and analyze data.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.date: 06/14/2017
ms.author: bholtorf

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

> [!NOTE]  
>   This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).

## Analyzing by Dimensions
The Dimensions functionality plays an important role in business intelligence, such as when defining analysis views. For more information, see [How to: Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

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

> [!NOTE]  
>   This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).

### Set up default dimensions for Customers, Vendors, and other accounts
You can assign a default dimension for a specific account. The dimension will be copied to the journal or document when you enter the account number on a line, but you can delete or change the code on the line if appropriate. You can also make a dimension required for posting an entry with a specific type of account.  

### Translate the names of dimensions
When you create a dimension, and especially a shortcut dimension, what you're actually creating is a custom field or column heading. If your business is international, you can provide translations for the name of the dimension. Documents that include the dimension will use the translated name, where applicable.   

### Example
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

## See Also
[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
