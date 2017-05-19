---
title: "Scenario Example: Defining Dynamic Allocations Based on Items Sold"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, dynamic allocation example"
ms.assetid: 6cf05dd5-8d45-4441-803b-0a9b1babbe7c
caps.latest.revision: 8
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Scenario Example: Defining Dynamic Allocations Based on Items Sold
This topic shows an example of how to define allocations by using the dynamic allocation method. In the example, you change the dynamic allocation of the costs for the SALES cost center to support the new cost object IT EQUIPMENT. IT EQUIPMENT packages have item numbers in the range from 8904\-W to 8924\-W. You use the previous year’s sales figures to calculate the share. The allocation is posted to the helping cost type 9903.  
  
> [!NOTE]  
>  The example uses the demo data in the [!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)].  
  
### To define dynamic allocations based on items sold in the previous year  
  
1.  In the **Search** box, enter **Cost Allocations**, and then choose the related link.  
  
2.  In the **\($ N\_1105 Cost Allocation $\)** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **\($ T\_1106\_1 ID $\)** field, press Enter or enter an ID.  
  
4.  In the **\($ T\_1106\_2 Level $\)** field, enter **1**.  
  
5.  In the **\($ T\_1106\_3 Valid From $\)** and **\($ T\_1106\_4 Valid To $\)** fields, enter appropriate dates.  
  
6.  In the **\($ T\_1106\_6 Cost Center Code $\)** field, enter **SALES**.  
  
7.  In the **\($ T\_1106\_10 Credit to Cost Type $\)** field, enter the cost type **9903**.  
  
8.  In the **\($ T\_1107\_5 Target Cost Type $\)** field, enter the cost type **9903**.  
  
9. In the **\($ T\_1107\_7 Target Cost Object $\)** field, choose **New** to create a new cost object IT EQUIPMENT and fill in fields as necessary. Select **IT EQUIPMENT**. Leave the **\($ T\_1107\_6 Target Cost Center $\)** field blank.  
  
10. In the **\($ T\_1107\_38 Allocation Target Type $\)** field, select **All Costs** to define how all accumulated costs are allocated.  
  
11. In the **\($ T\_1107\_30 Base $\)** field, select the allocation base **Items Sold \(Amount\)**.  
  
12. In the **\($ T\_1107\_31 No. Filter $\)** field, enter **8904\-W..8924\-W**.  
  
13. In the **\($ T\_1107\_34 Date Filter Code $\)** field, enter **Last Year**.  
  
14. On the **Home** tab, in the **Process** group, choose **Calculate Allocation Key** to calculate the share.  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] uses the previous years’ sales figures to calculate a share of 1596.50 LCY with 100 percent for the IT EQUIPMENT packages. This means that all of the items sold last year will be allocated to the cost object IT EQUIPMENT.  
  
## See Also  
 [Setting Filters for Dynamic Allocation Bases](../Finance/setting-filters-for-dynamic-allocation-bases.md)   
 [How to: Set Up Allocation Source and Targets](../Finance/how-to-set-up-allocation-source-and-targets.md)   
 [\($ B\_1131 Cost Allocation $\)](../Finance/-$-b_1131-cost-allocation-$-.md)   
 [Define and Allocate Costs](../Finance/define-and-allocate-costs.md)   
 [Terminology in Cost Accounting](../Finance/terminology-in-cost-accounting.md)   
 [About Cost Accounting](../Finance/about-cost-accounting.md)