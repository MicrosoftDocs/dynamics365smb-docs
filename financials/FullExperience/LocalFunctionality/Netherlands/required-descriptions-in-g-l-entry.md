---
title: "Required Descriptions in G-L Entry"
ms.custom: na
ms.date: "06-04-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "journal entries, required descriptions"
  - "general ledger, required descriptions"
ms.assetid: 22f1477f-b73b-4326-ac9f-4190a865aaa3
caps.latest.revision: 5
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# Required Descriptions in G-L Entry
When entering general journal lines on a form, the system fills in automatically the description field. This description will also be stored in the [\($ T\_17 G\/L Entry $\)](assetId:///2b5b8281-fbfa-4b7f-a154-a9ec61afadfe) after posting the journal. For a good audit trail, a more detailed description is desirable, when you post a journal line of type 'G\/L account'.  
  
 To force the user to enter a more detailed description, it is possible to choose if the system must fill in automatically the description of the G\/L account or leave the field blank. If the field [\($ T\_15\_11400 Omit Default Descr. in Jnl. Field $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_15_11400-omit-default-descr.-in-jnl.-field-$-.md) on the form [\($ N\_17 G\/L Account Card $\)](assetId:///866b5e10-d4e8-4b16-a5af-37ff7ced8abf) is checked, the system will not fill in the description field for that G\/L account when selected in a general journal line.  
  
 When posting the journal lines the system will check if all the description fields are filled in. If there is a blank description an error message will appear.  
  
> [!NOTE]  
>  Leaving the description field blank and check if all the description fields are filled in before posting, will only be done on the general journal windows in several application areas and on the local Cash Bank Giro windows.  
  
## See Also  
 [General Ledger\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/general-ledger-duplicate.md)