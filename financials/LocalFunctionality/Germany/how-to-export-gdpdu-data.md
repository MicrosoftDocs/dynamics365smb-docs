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
# How to: Export GDPdU Data
You can export financial data and tax data according to the process for data access and testability of digital documents (GDPdU). You can also select various options to be included in an XML file.  
  
 If there is no data to export, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] creates empty files.  
  
### To export GDPdU data  
  
1.  In the **Search** box, enter **Export Business Data**, and then choose the related link.  
  
2.  In the **GDPdU Export** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Starting Date**|Specifies the start date for the data export.<br /><br /> **NOTE:** If the data export source ../../includes period fields, the start date and the end date are used as filter values for the period fields.|  
    |**Ending Date**|Specifies the end date for the data export.|  
    |**Include Closing Date**|Specifies if the data export must include the closing date for the period.|  
  
3.  On the **Data Export Record Definition** FastTab, select the appropriate filters to identify the data export and data export record type. For more information, see [Process for Data Access and Testability of Digital Documents (GDPdU)](process-for-data-access-and-testability-of-digital-documents-gdpdu-.md).  
  
4.  To export the data, choose the **OK** button.  
  
    > [!WARNING]  
    >  During the export, any existing files, including the log file, will be overwritten. If you export the same data twice, the files from the first export are overwritten  
  
 You will be notified when the export completes. If you cancel the export, or if you close the window, you will also be notified that the export has completed, but the log folder will be empty. However, depending on your configuration, some files may have been exported, but the export might not be complete.  
  
## See Also  
 [Process for Data Access and Testability of Digital Documents (GDPdU)](process-for-data-access-and-testability-of-digital-documents-gdpdu-.md)