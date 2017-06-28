---
title: "Scenario Example: Defining Static Allocations Based on Allocation Ratio"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, static allocation example"
ms.assetid: 67eee307-bc51-4dcf-82e5-cb59d5628f1f
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
# Scenario Example: Defining Static Allocations Based on Allocation Ratio
Static allocation method is based on a definite value, such as square meters used, or an established allocation ratio such as 5:2:4.  
  
 This topic describes how to define three new allocation target cost objects for the allocation source PROD cost center using the established allocation ratio 5:2:4. The three target cost objects are ACCESSO, PAINT, and FITTINGS.  
  
> [!NOTE]  
>  The example uses the demo data in the [!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)].  
  
### To define the allocation source PROD cost center on the General FastTab  
  
1.  In the **Search** box, enter **Cost Allocation**, and then choose the related link.  
  
2.  In the **\($ N\_1105 Cost Allocation $\)** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **\($ T\_1106\_1 ID $\)** field, press Enter or enter an ID.  
  
4.  In the **\($ T\_1106\_2 Level $\)** field, enter **1**.  
  
5.  In the **\($ T\_1106\_3 Valid From $\)** and **\($ T\_1106\_4 Valid To $\)** fields, enter appropriate dates.  
  
6.  In the **\($ T\_1106\_6 Cost Center Code $\)** field, enter **PROD**.  
  
7.  In the **\($ T\_1106\_10 Credit to Cost Type $\)** field, enter the cost type **9903**.  
  
### To define the allocation target cost objects on the Lines FastTab  
  
1.  On the first line, in the **\($ T\_1107\_5 Target Cost Type $\)** field, enter **9903**.  
  
2.  On the first line, in the **\($ T\_1107\_7 Target Cost Object $\)** field, select **ACCESSO**.  
  
3.  On the first line, in the **\($ T\_1107\_38 Allocation Target Type $\)** field, select **All Costs** to define how all accrued costs are allocated.  
  
4.  On the first line, in the **\($ T\_1107\_30 Base $\)** field, select **Static** to use the static allocation method.  
  
5.  On the first line, in the **\($ T\_1107\_10 Share $\)** field, enter the allocation ratio **5**.  
  
6.  On the second line, in the **\($ T\_1107\_5 Target Cost Type $\)** field, enter **9903**.  
  
7.  On the second line, in the **\($ T\_1107\_7 Target Cost Object $\)** field, select **PAINT**.  
  
8.  On the second line, in the **\($ T\_1107\_38 Allocation Target Type $\)** field, select **All Costs** to define how all accrued costs are allocated.  
  
9. On the second line, in the **\($ T\_1107\_30 Base $\)** field, select **Static** to use the static allocation method.  
  
10. On the second line, in the **\($ T\_1107\_10 Share $\)** field, enter the allocation ratio **2**.  
  
11. On the third line, in the **\($ T\_1107\_5 Target Cost Type $\)** field, enter **9903**.  
  
12. On the third line, in the **\($ T\_1107\_7 Target Cost Object $\)** field, select **FITTINGS**.  
  
13. On the third line, in the **\($ T\_1107\_38 Allocation Target Type $\)** field, select **All Costs** to define how all accrued costs are allocated.  
  
14. On the third line, in the **\($ T\_1107\_30 Base $\)** field, select **Static** to use the static allocation method.  
  
15. On the third line, in the **\($ T\_1107\_10 Share $\)** field, enter the allocation ratio **4**.  
  
> [!IMPORTANT]  
>  [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] automatically calculates the **\($ T\_1107\_11 Percent $\)** field using a percentage rate that is dependent on all three allocation ratios that are entered in the **\($ T\_1107\_10 Share $\)** field for all three lines.  
  
## See Also  
 [How to: Set Up Allocation Source and Targets](../Finance/how-to-set-up-allocation-source-and-targets.md)   
 [\($ B\_1131 Cost Allocation $\)](../Finance/-$-b_1131-cost-allocation-$-.md)   
 [Define and Allocate Costs](../Finance/define-and-allocate-costs.md)   
 [Scenario Example: Defining Dynamic Allocations Based on Items Sold](../Finance/scenario-example-defining-dynamic-allocations-based-on-items-sold.md)   
 [Define and Allocate Costs](../Finance/define-and-allocate-costs.md)