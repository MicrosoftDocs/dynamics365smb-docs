---
title: "Dimension Set Entries Overview"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "dimension set entries, overview"
  - "dimensions, dimension set entries"
  - "entries, dimension set"
ms.assetid: c7cc0118-6924-43f9-adf8-08d771e571ba
caps.latest.revision: 16
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
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
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
# Dimension Set Entries Overview
This topic describes how dimension set entries are stored and posted in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)].  
  
## Dimension Sets  
 A dimension set is a unique combination of dimension values. It is stored as dimension set entries in the database. Each dimension set entry represents a single dimension value. The dimension set is identified by a common dimension set ID that is assigned to each dimension set entry that belongs to the dimension set.  
  
 The following example shows a dimension set that has three dimension set entries. The dimension set is identified by a dimension set ID, which is 108.  
  
|Dimension Set ID|Dimension Code|Dimension Value Code|Dimension Value Name|  
|----------------------|--------------------|--------------------------|--------------------------|  
|108|AREA|70|America North|  
|108|BUSINESSGROUP|HOME|Home|  
|108|DEPARTMENT|SALES|Sales|  
  
## Dimension Set Entries  
 Dimension sets are stored in the **Dimension Set Entry** table as dimension set entries with the same dimension set ID.  
  
 ![Dimension Entry overview](../ApplicationDesign/media/dimensionentrynav7.png "DimensionEntryNAV7")  
  
 When you create a new journal line, document header, or document line, you can specify a combination of dimension values. Instead of explicitly storing each dimension value in the database, a dimension set ID is assigned to the journal line, document header, or document line to specify the dimension set.  
  
 When you edit and close the **Edit Dimension Set Entries** window, a check is performed to see whether the combination of dimension values exists as a dimension set in the table. If the combination occurs in the table, then the corresponding dimension set ID is assigned to the journal line, document header, or document line. Otherwise, a new dimension set is added to the table, and the new dimension set ID is assigned to the journal line, document header, or document line.  
  
## Performance Improvement  
 By storing dimension sets once in the database, database space is preserved, and overall performance is improved.  
  
## See Also  
 [Design Details: Searching for Dimension Combinations](../ApplicationDesign/design-details-searching-for-dimension-combinations.md)   
 [Design Details: Table Structure](../ApplicationDesign/design-details-table-structure.md)   
 [Design Details: Codeunit 408 Dimension Management](../ApplicationDesign/design-details-codeunit-408-dimension-management.md)   
 [Design Details: Code Examples of Changed Patterns in Modifications](../ApplicationDesign/design-details-code-examples-of-changed-patterns-in-modifications.md)   
 [Design Details: Dimension Set Entries](../ApplicationDesign/design-details-dimension-set-entries.md)   
 [Dimension Set Entry](assetId:///d2bccaa5-90ff-4137-b56d-4c59eba5f533)   
 [Dimension Set Tree Node](assetId:///469c53b7-4b44-49e6-b914-445e84ed8525)   
 [Reclas. Dimension Set Buffer](assetId:///28a45482-7b26-4b9d-91ab-ab77c5ebe618)