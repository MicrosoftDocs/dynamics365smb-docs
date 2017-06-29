---
title: "How to: Export VAT Statements in XML Format"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "telematic VAT statements, exporting in XML format"
  - "exporting, VAT statements"
  - "VAT statements, exporting in XML format"
ms.assetid: 201f8c27-3a48-4ce9-a1c3-05c0a8bc8f15
caps.latest.revision: 12
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# How to: Export VAT Statements in XML Format
You can export a VAT statement in XML format and then submit it electronically to the tax authorities.  
  
 For more information, see the [Spanish Tax Agency](http://go.microsoft.com/fwlink/?LinkID=238181) website.  
  
### To export a VAT statement in XML format  
  
1.  In the **Search** box, enter **VAT Statement**, and then choose the appropriate link.  
  
2.  Select the required VAT statement, and then, on the **Actions** tab, choose **Telematic VAT**, and then choose **Generate XML file**.  
  
    > [!IMPORTANT]  
    >  The VAT statement name must be of the template type **One Column Report**.  
    >   
    >  In the standard version of ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, the VAT statement name for the 392 telematic statement is of the type **One Column Report**.  
  
3.  In the **XML VAT Declaration** window, on the **ADD INCLUDE<!--[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]-->** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10718\_N\_2\_1100000 VAT entries included $\)**|Specify if the VAT statement must include open entries, closed entries, or both open and closed entries.|  
    |**\($ B\_10718\_N\_2\_1100004 VAT entries included $\)**|Specify if the VAT statement must include only entries from the period that is specified in the **Date Filter** field, or also entries from previous periods.|  
    |**\($ B\_10718\_N\_2\_1100007 Additional Currency $\)**|Select to display the report amounts in the additional reporting currency.|  
  
4.  On the **VAT Statement Line** FastTab, specify a value for the **Date Filter** field.  
  
     Optionally, select additional filters.  
  
5.  Choose the **OK** button.  
  
6.  In the **XML Transference Format** window, verify that the VAT statement is set up as required, and then choose the **OK** button.  
  
 You can open or save the generated XML file. You can now submit the VAT statement to the tax authorities.  
  
## See Also  
 [How to: Create Templates for Telematic VAT Statements in XML File Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-create-templates-for-telematic-vat-statements-in-xml-file-format.md)   
 [How to: Export VAT Statements in Text Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-export-vat-statements-in-text-format.md)   
 XML VAT Declaration