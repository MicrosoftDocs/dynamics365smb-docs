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
  
|FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
|----------------------------------|---------------------------------------|  
|**Service item**|The price is automatically retrieved from the **Default Contract Value** field in the **Service Item** table and copied into the **Line Value** field.|  
|**Item**|Depending on the value in the **Contract Value Calc. Method** field in the **Service Mgt. Setup** table, the amount is retrieved from either the **Unit Price** or the **Unit Cost** field in the **Item** table. After that, this value is multiplied by the contents of the **Contract Value %** field in the **Service Mgt. Setup** table and divided by 100. This amount is copied into the **Line Value** field.<br /><br /> **NOTE:** If the **Contract Value Calc. Method** field is set to **None**, the contents of the **Line Value** field are not calculated.|  
|**Text description**|The contents of the **Line Value** field are set to zero.|  
  
## See Also  
 Service Item   
 Service Mgt. Setup   
 Default Contract Value   
 Contract Value Calc. Method   
 Unit Price   
 Unit Cost   
 Contract Value Percentage