---
title: "How to: Export VAT Statements in Text Format"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "telematic VAT statements, exporting in text format"
  - "exporting, VAT statements"
  - "VAT statements, exporting in text format"
ms.assetid: 8371369f-7158-4533-bc59-d528ef2f24b7
caps.latest.revision: 12
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# How to: Export VAT Statements in Text Format
You can export a VAT statement in text format and then submit it electronically to the tax authorities.  
  
 For more information, see the [Spanish Tax Agency](http://go.microsoft.com/fwlink/?LinkID=238181) website.  
  
### To export a VAT statement in text format  
  
1.  In the **Search** box, enter **VAT**, and then choose the link for the **Periodic Activities** area in the **Financial Management** department.  
  
2.  Under **Tasks**, choose **VAT Statements**.  
  
3.  Select the required VAT statement, and then, on the **Actions** tab, choose **Telematic VAT**, and then choose **Generate txt file**.  
  
    > [!IMPORTANT]  
    >  The VAT statement name must be of the template type **One Column Report**.  
    >   
    >  In the standard version of ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, the VAT statement name for the 320 telematic statement is of the type **One Column Report**.  
  
4.  In the **Telematic VAT Declaration** window, on the **ADD INCLUDE<!--[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]-->** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10715\_N\_2\_1 VAT entries included $\)**|Specify if the VAT statement must include open entries, closed entries, or both open and closed entries.|  
    |**\($ B\_10715\_N\_2\_4 VAT entries included $\)**|Specify if the VAT statement must include only entries from the period that is specified in the **Date Filter** field, or also entries from previous periods.|  
    |**\($ B\_10715\_N\_2\_8 Additional Currency $\)**|Select to display the report amounts in the additional reporting currency.|  
  
5.  On the **VAT Statement Line** FastTab, specify a value for the **Date Filter** field.  
  
     Optionally, select additional filters.  
  
6.  Choose the **OK** button.  
  
7.  In the **Transference Format** window, verify that the VAT statement is set up as required, and then choose the **OK** button.  
  
8.  Choose the **Open** button or choose the **Save** button.  
  
 You can now submit the VAT statement to the tax authorities.  
  
## See Also  
 [VAT Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/vat-reports.md)   
 [How to: Create Templates for Telematic VAT Statements in Text File Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-create-templates-for-telematic-vat-statements-in-text-file-format.md)   
 [How to: Export VAT Statements in XML Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-export-vat-statements-in-xml-format.md)   
 Telematic VAT Declaration