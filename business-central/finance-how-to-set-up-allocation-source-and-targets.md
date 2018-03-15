---
    title: How to Set Up Allocation Source and Targets | Microsoft Docs
    description: Each allocation consists of an allocation source and one or more allocation targets. The allocation source defines which costs will be allocated. The allocation targets determine where the costs will be allocated.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Up Allocation Source and Targets
Each allocation consists of an allocation source and one or more allocation targets. The allocation source defines which costs will be allocated. The allocation targets determine where the costs will be allocated.  

## To set up cost allocations  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cost Allocation**, and then chose the related link.  
2.  In the **Cost Allocation** window, choose the **Edit** action.  
3.  Enter an ID for the allocation source in the **ID** field.  
4.  Define a level as a number between 1 and 99 in the **Level** field. The allocation posting will follow the order of the levels.  
5.  Enter a cost type to define which cost types will be allocated in the **Cost Type Range** field. If all costs for a cost type are allocated, no range is defined.  
6.  Enter a cost center together with costs to be allocated in the **Cost Center Code** field.  
7.  Enter a cost object together with costs to be allocated in the **Cost Object Code** field. Most often, this field stays empty, because cost objects are rarely allocated to other cost objects.  
8.  Enter a cost type in the **Credit to Cost Type** field. The costs that are allocated will be credited to the source cost type. The credit posting will be posted to the cost type given here.  
9. On the **Lines** FastTab, define the allocation targets. On the first line, enter a cost type in the **Target Cost Type** field. It defines which cost type the allocation is debited to.  
10. On the first line, enter the first allocation target in the **Target Cost Center** field or **Target Cost Object** the field. These two fields define which cost center or cost object the allocation is debited to. You can only fill in one of these fields, but not both.  
11. Repeat the same steps on the second line to set up additional allocation targets.  
12. After you have set up the allocation target and sources, choose the **Calculate Allocation Key** action to calculate the total share values.  

> [!NOTE]  
>  Select the **Blocked** check box to deactivate the allocation setup.  

## See Also  
[Accounting for Costs](finance-manage-cost-accounting.md)  
 [Setting Filters for Dynamic Allocation Bases](finance-setting-filters-for-dynamic-allocation-bases.md)   
 [Scenario Example: Defining Static Allocations Based on Allocation Ratio](finance-scenario-example-defining-static-allocations-based-on-allocation-ratio.md)   
 [Scenario Example: Defining Dynamic Allocations Based on Items Sold](finance-scenario-example-defining-dynamic-allocations-based-on-items-sold.md)   
 [Defining and Allocating Costs](finance-define-and-allocate-costs.md)   
 [Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
