---
    title: How to Print Intrastat Reports
    description: All European Union (EU) companies must submit an Intrastat statistics report to the Instituto Nacional de Estatística (INE) detailing their trade with other EU countries/regions.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Print Intrastat Reports
All European Union (EU) companies must submit an Intrastat statistics report to the Instituto Nacional de Estatística (INE) detailing their trade with other EU countries/regions. Companies do not have to submit statistical declarations for the Intrastat system if their import and export totals are lower than the threshold set by their country/region.  

You can print and send required trade information in a file format approved by the tax authorities.  

## To print an Intrastat checklist  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Batch Name**|The required journal batch name.|  
    |**Type**|Select **Receipt** or **Shipment**.|  

3.  To get Intrastat entries, choose the **Get Entries** action.  

    > [!NOTE]  
    >  You can also make entries manually in the **Intrastat Journal** window.  

4.  Choose the **Make Declaration** action.  
5.  In the **Intrastat - Make Disk Tax Auth** batch job, expand the **Intrastat Jnl. Batch** FastTab, and then select the appropriate filters.  
6.  Expand the **Intrastat Jnl. Line** FastTab, select the appropriate filters, and then choose the **OK** button.  

The Intrastat information is exported, and you can save the data to a file, or open the file in the appropriate program.  

## See Also  
[Spain Local Functionality](spain-local-functionality.md)
