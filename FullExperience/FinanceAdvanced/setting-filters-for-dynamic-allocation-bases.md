---
title: "Setting Filters for Dynamic Allocation Bases"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, filters"
ms.assetid: 051afa62-315b-400c-bf1b-ad8cf8a91855
caps.latest.revision: 5
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
# Setting Filters for Dynamic Allocation Bases
The dynamic allocation method is based on changeable values. For example, the number of employees in a cost center or the items sold of a cost object in a specific time period. There are nine pre\-defined allocation bases and twelve dynamic date ranges. You set different filters based on the allocation base.  
  
## Setting Filters for Dynamic Allocation Bases  
 The following table shows which filters are possible for different allocation bases and which values are valid in the **\($ T\_1107\_31 No. Filter $\)** and **\($ T\_1107\_35 Group Filter $\)** fields. Press F1 in the **\($ T\_1107\_34 Date Filter Code $\)** field to read detailed descriptions.  
  
|**Base**|**\($ T\_1107\_31 No. Filter $\)**|**\($ T\_1107\_34 Date Filter Code $\)**|**\($ T\_1107\_32 Cost Center Filter $\)**|**\($ T\_1107\_33 Cost Object Filter $\)**|**\($ T\_1107\_35 Group Filter $\)**|  
|--------------|----------------------------------------|----------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------|  
|G\/L Entries|G\/L Account|Yes|Yes|Yes|N\/A|  
|G\/L Budget Entries|G\/L Account|Yes|Yes|Yes|G\/L Budget Name|  
|Cost Type Entries|Cost Type|Yes|Yes|Yes|N\/A|  
|Cost Budget Entries|Cost Type|Yes|Yes|Yes|Budget Name|  
|No of Employees|N\/A|Yes|Yes|Yes|N\/A|  
|Items Sold \(Qty\)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
|Items Purchased \(Qty\)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
|Items Sold \(Amount\)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
|Items Purchased \(Amount\)|Item No.|Yes|Yes|Yes|Inventory Posting Group|  
  
## See Also  
 [Scenario Example: Defining Dynamic Allocations Based on Items Sold](../Finance/scenario-example-defining-dynamic-allocations-based-on-items-sold.md)   
 [How to: Set Up Allocation Source and Targets](../Finance/how-to-set-up-allocation-source-and-targets.md)   
 [\($ B\_1131 Cost Allocation $\)](../Finance/-$-b_1131-cost-allocation-$-.md)   
 [Define and Allocate Costs](../Finance/define-and-allocate-costs.md)