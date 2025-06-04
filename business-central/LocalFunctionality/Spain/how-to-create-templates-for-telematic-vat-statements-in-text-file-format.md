---
title: Create Templates for Telematic VAT Statements in Text Format (ES)
description: Learn how to create templates for telematic VAT statements in text file format for electronic submission in the Spanish version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: telematic VAT statements, VAT statement, text file format, VAT statement template, Spanish version
ms.search.form: 10704, 10705
ms.date: 05/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create templates for telematic VAT statements in text file format

In order to submit VAT statements electronically, you must create templates to generate the required files. You can submit files in text format and in XML format. This procedure describes how to create templates for text files.  

Learn more in [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkID=238181) website.  

## Create a template for VAT statements in text file format  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement**, and then choose the appropriate link.  
1. Select the required VAT statement, and then choose the **Design txt file** action.  
1. On the **Transference Format** page, fill in the fields as described in the following table.  

    > [!IMPORTANT]  
    > The values for the fields are determined by the tax authorities.  
    >
    > Learn more in [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkID=238181) website.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Stmt. Name**|Specify the VAT statement name that this template is for.|  
    |**No.**|Specify the field number in the text file.|  
    |**Position**|Specify the position of this field in the text file.|  
    |**Length**|Specify the length of the field.|  
    |**Type**|Specify the type of the field. The available options are **Alphanumerical**, **Numerical**, **Fix**, **Ask**, and **Currency**.|  
    |**Subtype**|Specify the subtype of the field.<br><br/>The subtype specifies if the line must show only the integer part of an amount, the decimal part, or the full amount.|  
    |**Description**|Specify the text that you want to appear on the label.|  
    |**Value**|Specify the value for the label.|  
    |**Box**|Specify the box number from which to retrieve the data.|  

1. Repeat the previous step for additional lines in the VAT statement.  
1. Choose the **OK** button.  

This creates the template. Now, you can create a file that you can then submit to the tax authorities.  

## Related information

- [Export VAT Statements in Text Format](how-to-export-vat-statements-in-text-format.md)
- [Create Templates for Telematic VAT Statements in XML File Format](how-to-create-templates-for-telematic-vat-statements-in-xml-file-format.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
