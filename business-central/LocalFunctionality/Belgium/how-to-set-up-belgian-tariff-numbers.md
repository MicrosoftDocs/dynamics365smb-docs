---
    title: How to Set Up Belgian Tariff Numbers
    description: The Belgian customs and tax authorities have established an eight-digit item code for various tariff items.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Belgian Tariff Numbers
The Belgian customs and tax authorities have established an eight-digit item code for various tariff items.  

### To set up tariff numbers  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tariff Numbers**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **Tariff Numbers** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Conversion Factor**|Enter the conversion factor for the tariff number. The conversion factor is the factor by which you have to multiply the item unit to obtain the unit imposed by Intrastat. The conversion factor can be used when the item unit differs from the imposed Intrastat unit. The field is available when **Supplementary Units** is selected.|  
    |**Unit of Measure**|Enter the unit of measure for the tariff number. The field is available when **Supplementary Units** is selected.|  
    |**Weight Mandatory**|Select this field to show the weight of the items.|  

4.  Choose the **OK** button.  
  
## See Also  
 [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)   
 [Set Up Declaration Types](how-to-set-up-declaration-types.md)   
 [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)   
 [Export Intrastat Third-Party Declararations](how-to-export-intrastat-third-party-declararations.md)   
 [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)
