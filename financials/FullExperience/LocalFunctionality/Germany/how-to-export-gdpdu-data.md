---
title: "How to: Export GDPdU Data"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "exporting, GDPdU"
  - "GDPdU, exporting"
ms.assetid: 2868e4f3-c54c-49d5-9b9a-23cf0162921c
caps.latest.revision: 40
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Export GDPdU Data
You can export financial data and tax data according to the process for data access and testability of digital documents \(GDPdU\). You can also select various options to be included in an XML file.  
  
 If there is no data to export, ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> creates empty files.  
  
### To export GDPdU data  
  
1.  In the **Search** box, enter **Export Business Data**, and then choose the related link.  
  
2.  In the **GDPdU Export** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**\($ B\_11015\_N\_2\_1140000 Starting Date $\)**|Specifies the start date for the data export.<br /><br /> **NOTE:** If the data export source includes period fields, the start date and the end date are used as filter values for the period fields.|  
    |**\($ B\_11015\_N\_2\_1140002 Ending Date $\)**|Specifies the end date for the data export.|  
    |**\($ B\_11015\_N\_2\_1140084 Include Closing Date $\)**|Specifies if the data export must include the closing date for the period.|  
  
3.  On the **Data Export Record Definition** FastTab, select the appropriate filters to identify the data export and data export record type. For more information, see [Process for Data Access and Testability of Digital Documents \(GDPdU\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/process-for-data-access-and-testability-of-digital-documents-gdpdu-.md).  
  
4.  To export the data, choose the **OK** button.  
  
    > [!WARNING]  
    >  During the export, any existing files, including the log file, will be overwritten. If you export the same data twice, the files from the first export are overwritten  
  
 You will be notified when the export completes. If you cancel the export, or if you close the window, you will also be notified that the export has completed, but the log folder will be empty. However, depending on your configuration, some files may have been exported, but the export might not be complete.  
  
## See Also  
 [Process for Data Access and Testability of Digital Documents \(GDPdU\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/process-for-data-access-and-testability-of-digital-documents-gdpdu-.md)