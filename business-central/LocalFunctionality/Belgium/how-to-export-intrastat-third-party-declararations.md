---
    title: How to Export Intrastat Third-Party Declarations
    description: In Belgium, you must have a third-party declarant fill out the Intrastat declaration. The third-party declarant must be an external person or company.

    services: project-madeira 
    documentationcenter: ''
    author: sorenfriisalexandersen

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: soalex

---
# Export Intrastat Third-Party Declarations
In Belgium, you must have a third-party declarant fill out the Intrastat declaration. The third-party declarant must be an external person or company. 

## To export the third-party declaration  
Before you export the file, it's a good idea to preview the report. For more information, see [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md).  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journals**, and then choose the related link.  
2.  Choose the **Create File** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Nihil declaration**|Select if you do not have any trade transactions with European Union (EU) countries/regions and want to send an empty declaration.|  
    |**Counter party info**|Check this field to include counter party information in the Intrastat file (new requirement from 2019). The counter party information added to the file is taken from the **Country/Region of Origin Code** and **Partner ID** fields from the Intrastat Journal.|  
    |**Enterprise No./VAT Reg. No.**|Enter the enterprise or VAT registration number.|  
    
4.  Choose the **OK** button.  

Next, submit the declaration to the OneGate portal.  

## See Also  
 [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)   
 [Set Up Declaration Types](how-to-set-up-declaration-types.md)   
 [Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)   
 [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)   
 [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)
