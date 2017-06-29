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
  
|FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
|----------------------------------|---------------------------------------|  
|**Service item**|The cost is automatically retrieved from the **Default Contract Cost** field in the **Service Item** table and copied into the **Line Cost** field. The following formula is used to calculate the line cost:<br /><br /> Sales Unit Cost × Contract Value % ÷ 100|  
|**Item**|The cost is automatically retrieved from the **Unit Cost** field in the **Item** table and the **Contract Value %** field value in the **Service Mgt. Setup** table. The following formula is used to calculate the line cost:<br /><br /> Unit Cost × Contract Value % ÷ 100|  
|**Text description**|The value in the **Line Cost** field is set to zero.|  
  
## See Also  
 Service Item   
 Service Mgt. Setup   
 Contract Value Calc. Method   
 Unit Cost   
 Contract Value Percentage   
 Default Contract Cost