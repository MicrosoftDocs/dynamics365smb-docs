---
title: Setting Up Dimensions| Microsoft Docs
description: You can define the dimensions and dimension values you want to use to categorize journals and documents, such as sales orders and purchase orders.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/08/2016
ms.author: bholtorf

---
# Setting Up Dimensions
You can define the dimensions and dimension values to categorize journals and documents, such as sales orders and purchase orders. You set up dimensions in the **Dimensions** window, where you create one line for each dimension, such as *Project*, *Department*, *Area*, and *Salesperson*.

You also set up values for dimensions. For example, values might be departments in your company. Dimension values can be set up in a hierarchical structure similar to the chart of accounts, so that data can be broken down into various levels of granularity, and subsets of dimension values can be totaled. You can define as many dimensions and dimension values as you need, and everyone in your company can use them.

You can also set up some global and shortcut dimensions:  

* **Global dimensions** are used as filters, for example, on reports and batch jobs. You can use only two global dimensions, so choose dimensions you will use often.
* **Shortcut dimensions** are available as fields on journal and document lines. You can create up to six of these.  

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).

## Set up default dimensions for Customers, Vendors, and other accounts
You can assign a default dimension for a specific account. The dimension will be copied to the journal or document when you enter the account number on a line, but you can delete or change the code on the line if appropriate. You can also make a dimension required for posting an entry with a specific type of account.  

## Translate the names of dimensions
When you create a dimension, and especially a shortcut dimension, what you're actually creating is a custom field or column heading. If your business is international, you can provide translations for the name of the dimension. Documents that include the dimension will use the translated name, where applicable.   

## Example
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
**Note**: To set up a hierarchy, the codes must be in alphabetical order. This includes the codes of the dimension values that are provided in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

For **DEPARTMENT**, you add the following dimension values:

| Code | Name | Dimension Value Type |
| --- | --- | --- |
| ADMIN |Administration |Standard |
| PROD |Production |Standard |
| SALES |Sales |Standard |

With this set up, you then add your two dimensions as the two global dimensions in the **General Ledger Setup** window. This means that you can use AREA and DEPARTMENT as filters for general ledger entries, as well as on all reports and account schedules. Both global dimensions are also automatically available for use on entry lines and document headers as shortcut dimensions.  

With this set up, you can start adding dimensions to documents and journals. For more information, see [Dimensions](finance-dimensions.md).  

## See Also
[Dimensions](finance-dimensions.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
