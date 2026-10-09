---
title: Export Data for a Digital Audit [DE]
description: Financial and tax data can be exported in compliance with the digital audits process (GoBD/GDPdU), which adheres to German tax law.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: GoBD, GDPdU, digital audits, German tax law, German version
ms.search.form: 11002, 11003, 11004, 11007, 11008, 11009, 11014, 11026, 11027
ms.date: 10/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Export data for a digital audit in the German version

You can export financial data and tax data according to the process for digital audits (GoBD/GDPdU). You can also select various options to be included in an XML file.  

If there's no data to export, [!INCLUDE[prod_short](../../includes/prod_short.md)] creates empty files.  

### Export data for a digital audit

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export Business Data**, and then choose the related link.
1. On the **Export Business Data** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Starting Date**|Specifies the start date for the data export.<br><br/> **NOTE:** If the data export source includes period fields, the start date and the end date are used as filter values for the period fields.|  
    |**Ending Date**|Specifies the end date for the data export.|  
    |**Include Closing Date**|Specifies if the data export must include the closing date for the period.|  

1. On the **Data Export Record Definition** FastTab, select the appropriate filters to identify the data export and data export record type. Learn more in [Process for Digital Audits (GoBD/GDPdU)](process-for-digital-audits.md).
1. To export the data, choose the **OK** button.  

    > [!WARNING]  
    > If you export the same data twice, the files from the first export are overwritten.  

Business Central packages the exported files and the log file into a single *.zip* archive, and your browser downloads the archive when the export completes. If you cancel the export, or close the page before it finishes, no archive is downloaded. However, depending on your configuration, some data may have already been processed, so the export might not be complete.  

## Related information

[Process for Digital Audits (GoBD/GDPdU)](process-for-digital-audits.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
