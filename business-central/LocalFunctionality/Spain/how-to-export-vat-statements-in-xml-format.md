---
title: Export VAT Statements in XML Format
description: Learn how to export a VAT statement as an XML file in Business Central for Spain, select VAT entries, and review the XML transference format.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export VAT statements, VAT XML format, Spanish version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Export VAT statements in XML format

You can export a VAT statement in XML format and then submit it electronically to the tax authorities.  

Learn more at the [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkID=238181) website.  

## Steps to export a VAT statement in XML format  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Statement**, and then choose the appropriate link.  
1. Select the required VAT statement, and then choose the **Generate XML file** action.  

    > [!IMPORTANT]  
    > The VAT statement name must be of the template type **One Column Report**.  
    >
    > In the standard version of [!INCLUDE[prod_short](../../includes/prod_short.md)], the VAT statement name for the 392 telematic statement is of the type **One Column Report**.  

1. On the **XML VAT Declaration** page, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT entries included**|Specify if the VAT statement must include open entries, closed entries, or both open and closed entries.|  
    |**VAT entries included**|Specify if the VAT statement must include only entries from the period that is specified in the **Date Filter** field, or also entries from previous periods.|  
    |**Additional Currency**|Select to display the report amounts in the additional reporting currency.|  

1. On the **VAT Statement Line** FastTab, specify a value for the **Date Filter** field.  

   Optionally, select additional filters.  
1. Choose the **OK** button.  
1. On the **XML Transference Format** page, verify that the VAT statement is set up as required, and then choose the **OK** button.  

You can open or save the generated XML file. You can now submit the VAT statement to the tax authorities.  

## Related information

- [Create Templates for Telematic VAT Statements in XML File Format](how-to-create-templates-for-telematic-vat-statements-in-xml-file-format.md)
- [Export VAT Statements in Text Format](how-to-export-vat-statements-in-text-format.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
