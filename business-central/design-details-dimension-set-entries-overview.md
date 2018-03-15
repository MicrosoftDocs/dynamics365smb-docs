---
    title: Dimension Set Entries Overview | Microsoft Docs
    description: This topic describes how dimension set entries are stored and posted in Dynamcis 365.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: dimension
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Dimension Set Entries Overview
This topic describes how dimension set entries are stored and posted in [!INCLUDE[d365fin](includes/d365fin_md.md)].  
  
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
  
![Dimension Entry overview](media/dimensionentrynav7.png "DimensionEntryNAV7")  
  
When you create a new journal line, document header, or document line, you can specify a combination of dimension values. Instead of explicitly storing each dimension value in the database, a dimension set ID is assigned to the journal line, document header, or document line to specify the dimension set.  
  
When you edit and close the **Edit Dimension Set Entries** window, a check is performed to see whether the combination of dimension values exists as a dimension set in the table. If the combination occurs in the table, then the corresponding dimension set ID is assigned to the journal line, document header, or document line. Otherwise, a new dimension set is added to the table, and the new dimension set ID is assigned to the journal line, document header, or document line.  
  
## Performance Improvement  
By storing dimension sets once in the database, database space is preserved, and overall performance is improved.  
  
## See Also  
[Design Details: Searching for Dimension Combinations](design-details-searching-for-dimension-combinations.md)   
[Design Details: Table Structure](design-details-table-structure.md)   
[Design Details: Codeunit 408 Dimension Management](design-details-codeunit-408-dimension-management.md)   
[Design Details: Code Examples of Changed Patterns in Modifications](design-details-code-examples-of-changed-patterns-in-modifications.md)   
[Design Details: Dimension Set Entries](design-details-dimension-set-entries.md)   
