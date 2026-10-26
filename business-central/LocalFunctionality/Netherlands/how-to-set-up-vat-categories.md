---
title: Set Up Dutch VAT Declaration Categories
description: Map Dutch VAT statement amounts to electronic declaration categories, or use box numbers for VAT returns that use the DigitalTaxDecl reporting version.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT category codes, VAT XML elements, electronic VAT declaration, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up VAT categories

To use the electronic VAT declaration, you must set up a VAT category code for all XML elements in the electronic VAT declaration.  

You must set up all of the possible category and subcategory combinations that represent an XML element in the electronic VAT declaration. Then, you can map the VAT statement data directly to an XML element.  

## Set up a VAT category  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Electronic Tax Declaration VAT Categories**, and then choose the related link.
1. On the **Electronic Tax Declaration VAT Categories** page, choose the **New** action.
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique code for each category and subcategory combination. You can enter a maximum of 10 alphanumeric characters.|  
    |**Category**|Specify the main category option for the VAT statement.|  
    |**By Us (Domestic)**|Select a subcategory here if **Category** is **1. By Us (Domestic)**.|
    |**To Us (Domestic)**|Select a subcategory here if **Category** is **2. To Us (Domestic)**.|
    |**By Us (Foreign)**|Select a subcategory here if **Category** is **3. By Us (Foreign)**.|
    |**To Us (Foreign)**|Select a subcategory here if **Category** is **4. To Us (Foreign)**.|
    |**Calculation**|Select a subcategory here if **Category** is **5. Calculation**.|
    |**Optional**|Select to indicate that the XML element that is represented by the category code isn't required in the electronic VAT declaration.|  

1. Select the subcategory that matches the main category. Each category and subcategory combination must be unique.
1. On the VAT statement lines, assign the code in **Elec. Tax Decl. Category Code** to map the amounts to the corresponding XML element.

These category codes are used when you create a VAT declaration from **Electronic Tax Declarations**. VAT returns that use version **DigitalTaxDecl** use **Box No.** mappings instead.

## Map box numbers for VAT returns

For VAT returns with version **DigitalTaxDecl**, assign **Box No.** on the VAT statement lines that supply each amount. Use the identifiers exactly as shown in the following table.

| Amount | Turnover box number | VAT box number |
|---|---|---|
| Domestic supplies and services at the general rate | `1A-1` | `1A-2` |
| Domestic supplies and services at the reduced rate | `1B-1` | `1B-2` |
| Domestic supplies and services at other rates | `1C-1` | `1C-2` |
| Private use | `1D1` | `1D-2` |
| Supplies and services that aren't taxed | `1E` | Not applicable |
| Domestic supplies and services with reverse-charge VAT | `2A-1` | `2A-2` |
| Supplies to countries/regions outside the EU | `3A` | Not applicable |
| Supplies to countries/regions within the EU | `3B` | Not applicable |
| Installation and distance sales within the EU | `3C` | Not applicable |
| Taxed supplies from countries/regions outside the EU | `4A-1` | `4A-2` |
| Taxed supplies from countries/regions within the EU | `4B-1` | `4B-2` |
| Total VAT owed | Not applicable | `5A` |
| Input VAT | Not applicable | `5B` |
| VAT payable or refundable | Not applicable | `5G` |

These box numbers are separate from **Elec. Tax Decl. Category Code**. Review the suggested VAT return lines before submission to confirm that the mapped amounts are correct.

## Related information

- [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
- [Setting Up Electronic VAT and ICP Declarations](how-to-set-up-electronic-vat-and-icp-declarations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
