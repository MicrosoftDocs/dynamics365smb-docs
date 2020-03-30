---
    title: Defining and Allocating Costs | Microsoft Docs
    description: Cost allocations move costs and revenues between cost types, cost centers, and cost objects. You can define as many allocations as you need.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Defining and Allocating Costs
Cost allocations move costs and revenues between cost types, cost centers, and cost objects. You can define as many allocations as you need. Each allocation consists of:  

-   An allocation source.  
-   One or more allocation targets.  

The allocation source establishes which costs must be allocated, and the allocation targets determine where the costs must be allocated. For example, an allocation source can be the costs for the Electricity and Heating cost type. You allocate all electricity and heating costs to three cost centers: Workshop, Production, and Sales. These cost centers are your allocation targets.  

For each allocation source, you define an allocation level, a validity period, and a variant as grouping identifier. You can use a batch job to set filters to select allocation definitions and then run cost allocations automatically.  

For each allocation target, you define an allocation base. The allocation base can be either static or dynamic.  

-   Static allocation bases are based on a definite value, such as square footage or an established allocation ratio, such as 5:2:4.  
-   Dynamic allocation bases depend on changeable values, such as the number of employees in a cost center or sales revenue of a cost object throughout a certain time period.  

The following table describes a sequence of tasks, with links to the topics that describe them.

## Setting Up Allocation Source and Targets
Each allocation consists of an allocation source and one or more allocation targets. The allocation source defines which costs will be allocated. The allocation targets determine where the costs will be allocated.  

### To set up cost allocations  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cost Allocation**, and then chose the related link.  
2.  On the **Cost Allocation** page, choose the **Edit** action.  
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

## Setting Filters for Dynamic Allocation Bases
The dynamic allocation method is based on changeable values. For example, the number of employees in a cost center or the items sold of a cost object in a specific time period. There are nine pre-defined allocation bases and twelve dynamic date ranges. You set different filters based on the allocation base.  

### Setting Filters for Dynamic Allocation Bases  
 The following table shows which filters are possible for different allocation bases and which values are valid in the **No. Filter** and **Group Filter** fields. Press F1 in the **Date Filter Code** field to read detailed descriptions.  

|**Base**|**No. Filter**|**Date Filter Code**|**Cost Center Filter**|**Cost Object Filter**|**Group Filter**|  
|--------------|----------------------------------------|----------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------|  
|G/L Entries|G/L Account|Yes|Yes|Yes|N/A|  
|G/L Budget Entries|G/L Account|Yes|Yes|Yes|G/L Budget Name|  
|Cost Type Entries|Cost Type|Yes|Yes|Yes|N/A|  
|Cost Budget Entries|Cost Type|Yes|Yes|Yes|Budget Name|  
|No of Employees|N/A|Yes|Yes|Yes|N/A|  
|Items Sold (Qty)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
|Items Purchased (Qty)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
|Items Sold (Amount)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
|Items Purchased (Amount)|Item No.|Yes|Yes|Yes|Inventory Posting Group|

## Scenario 1: Defining Static Allocations Based on Allocation Ratio
Static allocation method is based on a definite value, such as square meters used, or an established allocation ratio such as 5:2:4.  

This topic describes how to define three new allocation target cost objects for the allocation source PROD cost center using the established allocation ratio 5:2:4. The three target cost objects are ACCESSO, PAINT, and FITTINGS.  

> [!NOTE]  
>  The example uses the demo data in the [!INCLUDE[d365fin](includes/d365fin_md.md)].  

### To define the allocation source PROD cost center on the General FastTab  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cost Allocation**, and then choose the related link.  
2.  On the **Cost Allocation** page, choose the **New** action.  
3.  In the **ID** field, press Enter or enter an ID.  
4.  In the **Level** field, enter **1**.  
5.  In the **Valid From** and **Valid To** fields, enter appropriate dates.  
6.  In the **Cost Center Code** field, enter **PROD**.  
7.  In the **Credit to Cost Type** field, enter the cost type **9903**.  

### To define the allocation target cost objects on the Lines FastTab  

1.  On the first line, in the **Target Cost Type** field, enter **9903**.  
2.  On the first line, in the **Target Cost Object** field, select **ACCESSO**.  
3.  On the first line, in the **Allocation Target Type** field, select **All Costs** to define how all accrued costs are allocated.  
4.  On the first line, in the **Base** field, select **Static** to use the static allocation method.  
5.  On the first line, in the **Share** field, enter the allocation ratio **5**.  
6.  On the second line, in the **Target Cost Type** field, enter **9903**.  
7.  On the second line, in the **Target Cost Object** field, select **PAINT**.  
8.  On the second line, in the **Allocation Target Type** field, select **All Costs** to define how all accrued costs are allocated.  
9. On the second line, in the **Base** field, select **Static** to use the static allocation method.  
10. On the second line, in the **Share** field, enter the allocation ratio **2**.  
11. On the third line, in the **Target Cost Type** field, enter **9903**.  
12. On the third line, in the **Target Cost Object** field, select **FITTINGS**.  
13. On the third line, in the **Allocation Target Type** field, select **All Costs** to define how all accrued costs are allocated.  
14. On the third line, in the **Base** field, select **Static** to use the static allocation method.  
15. On the third line, in the **Share** field, enter the allocation ratio **4**.  

> [!IMPORTANT]  
>  [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates the **Percent** field using a percentage rate that is dependent on all three allocation ratios that are entered in the **Share** field for all three lines.

## Scenario 2: Defining Dynamic Allocations Based on Items Sold
This topic shows an example of how to define allocations by using the dynamic allocation method. In the example, you change the dynamic allocation of the costs for the SALES cost center to support the new cost object IT EQUIPMENT. IT EQUIPMENT packages have item numbers in the range from 8904-W to 8924-W. You use the previous year’s sales figures to calculate the share. The allocation is posted to the helping cost type 9903.  

> [!NOTE]  
>  The example uses the demo data in the [!INCLUDE[d365fin](includes/d365fin_md.md)].  

### To define dynamic allocations based on items sold in the previous year  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cost Allocations**, and then choose the related link.  
2.  On the **Cost Allocation** page, choose the **New** action.  
3.  In the **ID** field, press Enter or enter an ID.  
4.  In the **Level** field, enter **1**.  
5.  In the **Valid From** and **Valid To** fields, enter appropriate dates.  
6.  In the **Cost Center Code** field, enter **SALES**.  
7.  In the **Credit to Cost Type** field, enter the cost type **9903**.  
8.  In the **Target Cost Type** field, enter the cost type **9903**.  
9. In the **Target Cost Object** field, choose **New** to create a new cost object IT EQUIPMENT and fill in fields as necessary. Select **IT EQUIPMENT**. Leave the **Target Cost Center** field blank.  
10. In the **Allocation Target Type** field, select **All Costs** to define how all accumulated costs are allocated.  
11. In the **Base** field, select the allocation base **Items Sold (Amount)**.  
12. In the **No. Filter** field, enter **8904-W..8924-W**.  
13. In the **Date Filter Code** field, enter **Last Year**.  
14. Choose the **Calculate Allocation Key** action to calculate the share.  

> [!IMPORTANT]  
>  [!INCLUDE[d365fin](includes/d365fin_md.md)] uses the previous years’ sales figures to calculate a share of 1596.50 LCY with 100 percent for the IT EQUIPMENT packages. This means that all of the items sold last year will be allocated to the cost object IT EQUIPMENT.

## See Also  
 [Setting Up Cost Accounting](finance-set-up-cost-accounting.md)   
 [Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md)   
 [Accounting for Costs](finance-manage-cost-accounting.md)   
 [Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md)   
 [About Cost Accounting](finance-about-cost-accounting.md)
