---
    title: Scenario Example - Defining Dynamic Allocations Based on Items Sold | Microsoft Docs
    description: This topic shows an example of how to define allocations by using the dynamic allocation method.
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
# Scenario Example: Defining Dynamic Allocations Based on Items Sold
This topic shows an example of how to define allocations by using the dynamic allocation method. In the example, you change the dynamic allocation of the costs for the SALES cost center to support the new cost object IT EQUIPMENT. IT EQUIPMENT packages have item numbers in the range from 8904-W to 8924-W. You use the previous year’s sales figures to calculate the share. The allocation is posted to the helping cost type 9903.  

> [!NOTE]  
>  The example uses the demo data in the [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## To define dynamic allocations based on items sold in the previous year  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cost Allocations**, and then choose the related link.  
2.  In the **Cost Allocation** window, choose the **New** action.  
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
 [Setting Filters for Dynamic Allocation Bases](finance-setting-filters-for-dynamic-allocation-bases.md)   
 [Set Up Allocation Source and Targets](finance-how-to-set-up-allocation-source-and-targets.md)   
 [Defining and Allocating Costs](finance-define-and-allocate-costs.md)   
 [Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md)   
 [About Cost Accounting](finance-about-cost-accounting.md)
