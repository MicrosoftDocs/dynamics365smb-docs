---
title: "Planning with Manual Transfer Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 5341bd45-2ca3-45cb-a0c9-8079e6f8ba3b
caps.latest.revision: 5
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# Planning with Manual Transfer Orders
As you can see from the [Replenishment System](../Topic/\($%20T_5700_5419%20Replenishment%20System%20$\).md) field on a SKU card, the planning system can be set up to create transfer orders to balance supply and demand across locations.  
  
 In addition to such automatic transfer orders, you may sometimes need to perform a general move of inventory quantities to another location, irrespective of existing demand. For this purpose you would manually create a transfer order for the quantity to move. To ensure that the planning system does not try to manipulate this manual transfer order, you must set the [Planning Flexibility](../Topic/\($%20T_5741_99000755%20Planning%20Flexibility%20$\).md) field on the transfer line\(s\) to None.  
  
 Contrarily, if you do want the planning system to adjust the transfer order quantities and [dates](../Topic/\($%20T_5741_39%20Receipt%20Date%20$\).md) to existing demand, you must set the Planning Flexibility field to the default value, Unlimited.