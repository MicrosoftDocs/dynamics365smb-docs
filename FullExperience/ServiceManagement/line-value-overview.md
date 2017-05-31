---
title: "Line Value Overview"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service contracts, line value"
ms.assetid: 88f29f3d-0987-47dc-9804-5cbaea2938a9
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
# Line Value Overview
The **Line Value** field is filled in as described in the following table.  
  
|[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|----------------------------------|---------------------------------------|  
|**Service item**|The price is automatically retrieved from the **Default Contract Value** field in the **Service Item** table and copied into the **Line Value** field.|  
|**Item**|Depending on the value in the **Contract Value Calc. Method** field in the **Service Mgt. Setup** table, the amount is retrieved from either the **Unit Price** or the **Unit Cost** field in the **Item** table. After that, this value is multiplied by the contents of the **Contract Value %** field in the **Service Mgt. Setup** table and divided by 100. This amount is copied into the **Line Value** field.<br /><br /> **NOTE:** If the **Contract Value Calc. Method** field is set to **None**, the contents of the **Line Value** field are not calculated.|  
|**Text description**|The contents of the **Line Value** field are set to zero.|  
  
## See Also  
 [\($ T\_5940 Service Item $\)](../Topic/\($%20T_5940%20Service%20Item%20$\).md)   
 [\($ N\_5919 Service Mgt. Setup $\)](../Topic/\($%20N_5919%20Service%20Mgt.%20Setup%20$\).md)   
 [\($ T\_5940\_25 Default Contract Value $\)](../Topic/\($%20T_5940_25%20Default%20Contract%20Value%20$\).md)   
 [\($ T\_5911\_64 Contract Value Calc. Method $\)](../Topic/\($%20T_5911_64%20Contract%20Value%20Calc.%20Method%20$\).md)   
 [\($ T\_27\_18 Unit Price $\)](../Topic/\($%20T_27_18%20Unit%20Price%20$\).md)   
 [\($ T\_27\_22 Unit Cost $\)](../Finance/-$-t_27_22-unit-cost-$-.md)   
 [\($ T\_5911\_65 Contract Value Percentage $\)](../Topic/\($%20T_5911_65%20Contract%20Value%20Percentage%20$\).md)