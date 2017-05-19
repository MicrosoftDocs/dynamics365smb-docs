---
title: "Line Cost Overview"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service contracts, line costs"
ms.assetid: d7cf5216-1b06-4246-9bd0-0803c58ef37e
caps.latest.revision: 6
ms.author: "edupont"
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
# Line Cost Overview
The **Line Cost** field is filled in as described in the following table.  
  
|[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|----------------------------------|---------------------------------------|  
|**Service item**|The cost is automatically retrieved from the **Default Contract Cost** field in the **Service Item** table and copied into the **Line Cost** field. The following formula is used to calculate the line cost:<br /><br /> Sales Unit Cost × Contract Value % ÷ 100|  
|**Item**|The cost is automatically retrieved from the **Unit Cost** field in the **Item** table and the **Contract Value %** field value in the **Service Mgt. Setup** table. The following formula is used to calculate the line cost:<br /><br /> Unit Cost × Contract Value % ÷ 100|  
|**Text description**|The value in the **Line Cost** field is set to zero.|  
  
## See Also  
 [\($ T\_5940 Service Item $\)](../Topic/\($%20T_5940%20Service%20Item%20$\).md)   
 [\($ N\_5919 Service Mgt. Setup $\)](../Topic/\($%20N_5919%20Service%20Mgt.%20Setup%20$\).md)   
 [\($ T\_5911\_64 Contract Value Calc. Method $\)](../Topic/\($%20T_5911_64%20Contract%20Value%20Calc.%20Method%20$\).md)   
 [\($ T\_27\_22 Unit Cost $\)](../Finance/-$-t_27_22-unit-cost-$-.md)   
 [\($ T\_5911\_65 Contract Value Percentage $\)](../Topic/\($%20T_5911_65%20Contract%20Value%20Percentage%20$\).md)   
 [\($ T\_5940\_86 Default Contract Cost $\)](../Topic/\($%20T_5940_86%20Default%20Contract%20Cost%20$\).md)