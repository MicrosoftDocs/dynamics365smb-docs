---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Planning with Manual Transfer Orders
As you can see from the [Replenishment System](../FullExperience/\($%20T_5700_5419%20Replenishment%20System%20$\).md) field on a SKU card, the planning system can be set up to create transfer orders to balance supply and demand across locations.  
  
 In addition to such automatic transfer orders, you may sometimes need to perform a general move of inventory quantities to another location, irrespective of existing demand. For this purpose you would manually create a transfer order for the quantity to move. To ensure that the planning system does not try to manipulate this manual transfer order, you must set the [Planning Flexibility](../FullExperience/\($%20T_5741_99000755%20Planning%20Flexibility%20$\).md) field on the transfer line\(s\) to None.  
  
 Contrarily, if you do want the planning system to adjust the transfer order quantities and [dates](../FullExperience/\($%20T_5741_39%20Receipt%20Date%20$\).md) to existing demand, you must set the Planning Flexibility field to the default value, Unlimited.