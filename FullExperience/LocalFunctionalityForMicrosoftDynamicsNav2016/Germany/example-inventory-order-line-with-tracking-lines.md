---
title: "Example - Inventory Order Line with Tracking Lines"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "inventory, tracking example"
  - "physical inventory, tracking example"
ms.assetid: 64d44c98-e3cc-4782-b588-9bb060394676
caps.latest.revision: 5
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# Example - Inventory Order Line with Tracking Lines
The physical inventory order line should contain the following data:  
  
-   Item No.: 80216\-V  
  
-   Location Code: BLUE  
  
-   The fields Variant Code and Bin Code may be blank.  
  
 There is a check mark in the field [\($ T\_5005351\_53 Use Tracking Lines $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_53-use-tracking-lines-$-.md) on the physical inventory order line and the item 80216\-V should be posted all time with lot nos. according to the item tracking code.  
  
 The posting date on the physical inventory order header should be 12\/31\/2002.  
  
 The expected quantity of the item 80216\-V at the location BLUE on 12\/31\/2001 should be 120 pieces.  
  
 The quantity on stock consists of the following lots:  
  
## The expected Item Tracking Lines:  
  
|**Lot No.**|**Quantity**|  
|-----------------|------------------|  
|CH1001|80|  
|CH1003|30|  
|CH1006|10|  
|**Total**|**120**|  
  
 There had been recorded the following physical inventory recording lines for the item 80216\-V, location code BLUE:  
  
## Recorded Lot Nos. on the Physical Inventory Recording Lines:  
  
|**Lot No.**|**Quantity**|  
|-----------------|------------------|  
|CH1001|80|  
|CH1002|12|  
|CH1003|20|  
|**Total**|**112**|  
  
 When finishing the physical inventory order the program will calculate for the item 80216\-V at the location BLUE a negative adjustment of 8 pieces and will create the following entries:  
  
## Item Tracking lines to post:  
  
|**Lot No.**|**Expected Quantity**|**Recorded Quantity**|**Quantity to post**|  
|-----------------|---------------------------|---------------------------|--------------------------|  
|CH1001|80|80|0|  
|CH1002|0|12|\+ 12|  
|CH1003|30|20|\- 10|  
|CH1006|10|0|\- 10|  
|**Total**|**120**|**112**|**\- 8**|  
  
## See Also  
 [Physical Inventory Order Lines With Item Tracking Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-order-lines-with-item-tracking-lines.md)