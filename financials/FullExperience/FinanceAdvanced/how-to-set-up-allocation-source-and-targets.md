---
title: "How to: Set Up Allocation Source and Targets"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, allocation source and targets"
ms.assetid: 2bc08320-ce0e-4428-9e77-dc7ee7e25d47
caps.latest.revision: 13
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
# How to: Set Up Allocation Source and Targets
Each allocation consists of an allocation source and one or more allocation targets. The allocation source defines which costs will be allocated. The allocation targets determine where the costs will be allocated.  
  
### To set up cost allocations  
  
1.  In the **Search** box, enter **\($ N\_1105 Cost Allocation $\)**, and then chose the related link.  
  
2.  In the **\($ N\_1105 Cost Allocation $\)** window, on the **Home** tab, choose **Edit**.  
  
3.  Enter an ID for the allocation source in the **\($ T\_1106\_1 ID $\)** field.  
  
4.  Define a level as a number between 1 and 99 in the **\($ T\_1106\_2 Level $\)** field. The allocation posting will follow the order of the levels.  
  
5.  Enter a cost type to define which cost types will be allocated in the **\($ T\_1106\_5 Cost Type Range $\)** field. If all costs for a cost type are allocated, no range is defined.  
  
6.  Enter a cost center together with costs to be allocated in the **\($ T\_1106\_6 Cost Center Code $\)** field.  
  
7.  Enter a cost object together with costs to be allocated in the **\($ T\_1106\_7 Cost Object Code $\)** field. Most often, this field stays empty, because cost objects are rarely allocated to other cost objects.  
  
8.  Enter a cost type in the **\($ T\_1106\_10 Credit to Cost Type $\)** field. The costs that are allocated will be credited to the source cost type. The credit posting will be posted to the cost type given here.  
  
9. On the **Lines** FastTab, define the allocation targets. On the first line, enter a cost type in the **\($ T\_1107\_5 Target Cost Type $\)** field. It defines which cost type the allocation is debited to.  
  
10. On the first line, enter the first allocation target in the **\($ T\_1107\_6 Target Cost Center $\)** field or **\($ T\_1107\_7 Target Cost Object $\)** the field. These two fields define which cost center or cost object the allocation is debited to. You can only fill in one of these fields, but not both.  
  
11. Repeat the same steps on the second line to set up additional allocation targets.  
  
12. After you have set up the allocation target and sources, on the **Home** tab, in the **Process** group, choose **Calculate Allocation Key** to calculate the total share values.  
  
> [!NOTE]  
>  Select the **\($ T\_1106\_30 Blocked $\)** check box to deactivate the allocation setup.  
  
## See Also  
 [Setting Filters for Dynamic Allocation Bases](../Finance/setting-filters-for-dynamic-allocation-bases.md)   
 [Scenario Example: Defining Static Allocations Based on Allocation Ratio](../Finance/scenario-example-defining-static-allocations-based-on-allocation-ratio.md)   
 [Scenario Example: Defining Dynamic Allocations Based on Items Sold](../Finance/scenario-example-defining-dynamic-allocations-based-on-items-sold.md)   
 [Define and Allocate Costs](../Finance/define-and-allocate-costs.md)   
 [Terminology in Cost Accounting](../Finance/terminology-in-cost-accounting.md)