---
title: "How to: Create Templates for Telematic VAT Statements in Text File Format"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "telematic VAT statements, exporting in text format"
  - "templates, telematic VAT statements"
  - "VAT statements, exporting in text format"
  - "telematic VAT statements, templates"
ms.assetid: 462ab1df-dd0b-414d-852e-27566dccf6be
caps.latest.revision: 12
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# How to: Create Templates for Telematic VAT Statements in Text File Format
In order to submit VAT statements electronically, you must create templates to generate the required files. You can submit files in text format and in XML format. This procedure describes how to create templates for text files.  
  
 For more information, see the [Spanish Tax Agency](http://go.microsoft.com/fwlink/?LinkID=238181) website.  
  
### To create a template for VAT statements in text file format  
  
1.  In the **Search** box, enter **VAT Statement**, and then choose the appropriate link.  
  
2.  Select the required VAT statement, and then, on the **Actions** tab, choose **Telematic VAT**, and then choose **Design txt file**.  
  
3.  In the **Transference Format** window, fill in the fields as described in the following table.  
  
    > [!IMPORTANT]  
    >  The values for the fields are determined by the tax authorities.  
    >   
    >  For more information, see the [Spanish Tax Agency](http://go.microsoft.com/fwlink/?LinkID=238181) website.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**VAT Stmt. Name**|Specify the VAT statement name that this template is for.|  
    |**No.**|Specify the field number in the text file.|  
    |**Position**|Specify the position of this field in the text file.|  
    |**Length**|Specify the length of the field.|  
    |**Type**|Specify the type of the field. The available options are **Alphanumerical**, **Numerical**, **Fix**, **Ask**, and **Currency**.|  
    |**Subtype**|Specify the subtype of the field.<br /><br /> The subtype specifies if the line must show only the integer part of an amount, the decimal part, or the full amount.|  
    |**Description**|Specify the text that you want to appear on the label.|  
    |**Value**|Specify the value for the label.|  
    |**Box**|Specify the box number from which to retrieve the data.|  
  
4.  Repeat the previous step for additional lines in the VAT statement.  
  
5.  Choose the **OK** button.  
  
 This creates the template. Now, you can create a file that you can then submit to the tax authorities.  
  
## See Also  
 [How to: Export VAT Statements in Text Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-export-vat-statements-in-text-format.md)   
 [How to: Create Templates for Telematic VAT Statements in XML File Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-create-templates-for-telematic-vat-statements-in-xml-file-format.md)   
 [AEAT Transference Format](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-t_10705-aeat-transference-format-$-.md)