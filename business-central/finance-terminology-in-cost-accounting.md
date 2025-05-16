---
title: Terminology in cost accounting
description: This article defines the key terms that are used in cost accounting, such as allocation key and allocation source.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.search.form: 1123
ms.date: 07/25/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Terminology in cost accounting

This article defines the key terms that are used in cost accounting.  

## Key terms

 The following table shows definitions of the key terms in cost accounting.  

|**Term**|**Definition**|  
|--------------|--------------------|  
|Allocation key|The allocation key is the basis that is used to allocate costs. It's typically a quantity, such as square meters occupied, number of employees, or work hours used. For example, two departments, with 20 and 10 employees respectively, share canteen costs. The costs are distributed between the departments by using an allocation key that represents the number of employees. Two thirds of the costs are allocated to the first department, and one third of the costs are allocated to the second department.|  
|Allocation source|The allocation source establishes which costs are allocated. Allocations are defined in allocation source and allocation target tables. Each allocation consists of an allocation source and one or more allocation targets. For example, all costs for the heating cost type, which is an allocation source, can be allocated to the workshop, production, and sales cost centers, which are three allocation targets.|  
|Allocation target|The allocation targets determine where the costs are allocated. Allocations are defined in allocation source and allocation target tables. Each allocation consists of an allocation source and one or more allocation targets. For example, all costs for the heating cost type, which is an allocation source, can be allocated to the workshop, production, and sales cost centers, which are three allocation targets.|  
|Cost accounting|In cost accounting, actual costs of operations, processes, departments, or products are recorded. These costs are allocated to cost centers and cost objects by using different cost allocation methods. Managers use statistics and reports, such as cost distribution sheet and profit and loss analysis to make decisions and reduce costs. Cost accounting retrieves data from the general ledger, but works independently. Therefore transactions posted in cost accounting don't affect the data in the general ledger.|  
|Cost type|The chart of cost types has the same function as the chart of accounts in the general ledger. They're often structured similarly. Therefore it's possible to transfer the general ledger chart of accounts to the chart of cost types and then modify it. The chart of cost types can also be created from scratch.|  
|Cost center|Cost centers are most often departments and profit centers that are largely responsible for company’s costs and income. Cost centers can be synchronized with dimensions in the general ledger. It's also possible to add new cost centers and define their own sorting with subtotals.|  
|Cost object|Cost objects are products, product groups or services of a company, the finished goods of a company, that in the end carries the costs. Cost objects can be synchronized with dimensions in the general ledger. It's also possible to add new cost objects and define their own sorting with subtotals.|  
|Cost allocation|Cost allocation is a process of allocating costs to cost centers or cost objects. For example, the wage of the truck driver of the sales department is allocated to the sales department cost center. It isn't necessary to allocate the wage cost to other cost centers. Another example is that the cost of an expensive computer system is allocated to the products of the company that use the system.|  
|Dynamic allocation|Dynamic allocations are dependent on changeable allocation bases, for example, the number of department employees, or the sales revenue of the project within a certain period of time. There are nine predefined dynamic allocation bases that users can define by using five filters.|  
|Direct cost|Direct costs are the costs that can be directly allocated to a cost object, for example, material purchase for a specific product.|  
|Fixed cost|Fixed costs are the costs that aren't dependent on the level of goods or services produced by the company. They tend to be time-related, such as salary or rent being paid per month. They are in contrast to variable costs, which are volume-related, and are paid per quantity produced.|  
|Indirect cost|Indirect costs aren't directly accountable to a cost object, such as a particular function or product. Indirect costs may be either fixed or variable. Indirect costs can be tax, administration, personnel, and security costs and are also known as overhead costs.|  
|Level|Level is used to define allocation order. Level is defined as a number between 1 and 99. The allocation posting follows the order of the levels. For example, level ensures that first administration is allocated to workshop before workshop is allocated to vehicle and production.|  
|Static allocation|Static allocations are based on a fixed set of values, for example, the square meters used, or an established allocation ratio, such as 5:2:4.|  
|Operational cost|Operational costs are the recurring expenses, which are related to the operation of a business, a device, and a component.|  
|Overhead cost|Overhead costs refer to ongoing expenses of operating a business. They're all costs on the income statement except for direct labor, direct materials, and direct expenses. Overhead costs include accounting fees, advertising, depreciation, insurance, interest, legal fees, rent, repairs, supplies, taxes, telephone bills, travel, and utilities costs.|  
|Step variable cost|Step variable costs are costs that change dramatically at certain points because they involve large purchases that can't be spread out over time. For example, one employee can produce 100 tables in a month. The employee’s wage is constant over a production range of 1 to 100 tables. If the company wants to produce 110 tables, the company needs two employees. So the cost will double.|  
|Share|The portion or part that is allocated among cost centers or cost objects.|  
|Static weighting|Costs are allocated according to allocation keys, which can be modified by using a multiplier. <br />For example, two departments, with 20 and 10 employees respectively, share canteen costs. The costs are distributed between the departments by using an allocation key that represents the number of employees that eat in the canteen. In the first department, only five employees eat in the canteen, so this department has a multiplier of 0.25. The basis for allocation is 20 x 0.25 = 5. The total number of employees that eat in the canteen is 15. One third of the costs are allocated to the first department and two thirds of the costs are allocated to the second department.|  
|Variable cost|Variable costs are expenses that change in proportion to the activity of a business. Variable costs are the sum of marginal costs over all units produced. Fixed costs and variable costs make up the two components of total costs.|  
|Variant|A variant is used as an optional user-defined label for allocations. The purpose of the label is to filter groups of allocation.|  

## Related information

 [About Cost Accounting](finance-about-cost-accounting.md)  
 [Accounting for Costs](finance-manage-cost-accounting.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
