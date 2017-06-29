---
title: "Fault Reporting"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fault, codes"
  - "fault, reporting"
ms.assetid: 1fcd9c22-2d09-4e40-b1b1-5e6c922f0764
caps.latest.revision: 7
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
# Fault Reporting
To set up service standards and responses for your company, you can establish how to capture and record fault information and what action to take in response to service items. The [!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)] for [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] provides four options, from which you can select one in the **General** FastTab of the **Service Mgt. Setup** window. Your selection serves as the default implementation for your service application.  
  
 The following table describes the various fault reporting levels.  
  
|Fault|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|-----------|---------------------------------------|  
|**None**|No reporting codes are used.|  
|**Fault**|Codes are listed in the **Fault Codes** table. These codes can identify service item faults or actions to take on service items. You can cluster related codes into **Fault Area Code** groupings|  
|**Fault \+ Symptom**|You provide a combination of codes in the **Fault Codes** and **Symptom Codes** tables. Typical symptom codes include indicators that a customer might use to describe a problem, such as noise or quality.|  
|**Fault \+ Symptom \+ Area \(IRIS\)**|You use **Fault**, **Symptom**, and **Fault Area** codes, as an implementation of the International Repair Coding System \(IRIS\).|  
  
 To complete the setup of fault reporting, you can also specify what repairs or resolutions are associated with a fault or defect. For more information, see Fault\-Resolution Codes Relationships.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Set up common fault codes and areas. Use these to describe typical faults.|[How to: Set Up Fault Codes](../Service/how-to-set-up-fault-codes.md)|  
|Set up a list of typical symptoms that a customer might use to describe certain faults.|[How to: Set Up Symptom Codes](../Service/how-to-set-up-symptom-codes.md)|  
|Establish a list of typical repair methods or resolutions to service problems.|[How to: Set Up Resolution Codes](../Service/how-to-set-up-resolution-codes.md)|  
  
## See Also  
 Fault Code   
 Fault Reason Code   
 Symptom Code   
 Resolution Code