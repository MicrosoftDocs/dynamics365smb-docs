---
title: Create templates for telematic VAT statements in XML format (ES)
description: Learn how to create templates for telematic VAT statements in XML format in the Spanish version of Business Central to enable electronic submission.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT statement template, telematic VAT statement, XML file format, electronic submission, Spanish version
ms.search.form: 10710
ms.date: 05/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create templates for telematic VAT statements in XML file format

In order to submit VAT statements electronically, you must create templates to generate the required files. You can submit files in text format and in XML format. This procedure describes how to create templates for XML files.  

Learn more in [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkID=238181) website.  

## Create a template for VAT statements in XML file format  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement**, and then choose the appropriate link.  
1. Select the required VAT statement, and then choose the **Design XML file** action.  
1. On the **XML Transference Format** page, fill in the fields as described in the following table.  

    > [!IMPORTANT]  
    > The values for the fields are determined by the tax authorities.  
    >
    > Learn more in [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkID=238181) website.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Stmt. Name**|Specify the VAT statement name that this template is for.|  
    |**No.**|Specify the field number in the text file.|  
    |**Line Type**|Specify whether the VAT statement line type is an XML element or an XML attribute.|  
    |**Indentation Level**|Specify the indentation level for the label. This level is used to format the XML file.|  
    |**Parent Line No.**|Specify the line number of the parent line that the current line is indented under.|  
    |**Value Type**|Specify the subtype of the field.<br><br/> The subtype specifies if the line must show only the integer part of an amount, the decimal part, or the full amount.|  
    |**Description**|Specify the text that you want to appear on the label.|  
    |**Value**|Specify the value for the label.|  
    |**Box**|Specify the box number from which to retrieve the data.|  
    |**Ask**|Specifies if the **Value** field can be changed before you create the XML file.|  
    |**Exists Amount**|Select to include the existing amount.|  

1. Repeat the previous step for additional lines in the VAT statement.  
1. Choose the **OK** button.  

This creates the template. Now, you can create a file that you can then submit to the tax authorities.  

## Related information

- [Export VAT Statements in XML Format](how-to-export-vat-statements-in-xml-format.md)   
- [Create Templates for Telematic VAT Statements in Text File Format](how-to-create-templates-for-telematic-vat-statements-in-text-file-format.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
