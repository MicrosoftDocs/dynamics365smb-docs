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
# How to: Set Up Belgian Tariff Numbers
The Belgian customs and tax authorities have established an 8\-digit item code for various tariff items.  
  
### To set up tariff numbers  
  
1.  In the **Search** box, enter **Tariff Numbers**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **Tariff Numbers** window, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**Conversion Factor**|Enter the conversion factor for the tariff number. The conversion factor is the factor by which you have to multiply the item unit to obtain the unit imposed by Intrastat. The conversion factor can be used when the item unit differs from the imposed Intrastat unit. The field is available when **Supplementary Units** is selected.|  
    |**Unit of Measure**|Enter the unit of measure for the tariff number. The field is available when **Supplementary Units** is selected.|  
    |**Weight Mandatory**|Select this field to show the weight of the items.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Belgian Intrastat Reporting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-intrastat-reporting.md)   
 [How to: Set Up Declaration Types](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-declaration-types.md)   
 [How to: Set Up Intrastat Establishment Numbers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-intrastat-establishment-numbers.md)   
 [How to: Export Intrastat Third\-Party Declararations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-export-intrastat-third-party-declararations.md)   
 [How to: Print the Intrastat Form Report](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-the-intrastat-form-report.md)