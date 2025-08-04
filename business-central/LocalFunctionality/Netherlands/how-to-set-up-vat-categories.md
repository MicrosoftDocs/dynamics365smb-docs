---
title: How to Set Up VAT Categories
description: Learn how to set up VAT category codes for all XML elements required in the electronic VAT declaration.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT category codes, VAT XML elements, electronic VAT declaration, Dutch version, Netherlands
ms.date: 03/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up VAT categories

To use the electronic VAT declaration, you must set up a VAT category code for all XML elements in the electronic VAT declaration.  

You must set up all of the possible category and subcategory combinations that represent an XML element in the electronic VAT declaration. Then, you can map the VAT statement data directly to an XML element.  

## Set up a VAT category  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax. Decl. VAT Categories**, and then choose the related link.  
1. On the **Elec. Tax. Decl. VAT Categories** page, choose the **New** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique code for each category and subcategory combination. You can enter a maximum of 10 alphanumeric characters.|  
    |**Category**|Specify the main category option for the VAT statement.|  
    |**By Us (Domestic)**|The subcategory for the VAT Statement.<br><br/> Select a subcategory here if the **Category** field displays **By Us (Domestic)**.|  
    |**To Us (Domestic)**|The subcategory for the VAT Statement.<br><br/> Select a subcategory here if the **Category** field displays **To Us (Domestic)**.|  
    |**By Us (Foreign)**|The subcategory for the VAT Statement.<br><br/> Select a subcategory here if the **Category** field displays **By Us (Foreign)**.|  
    |**To Us (Foreign)**|The subcategory for the VAT Statement.<br><br/> Select a subcategory here if the **Category** field displays **To Us (Foreign)**.|  
    |**Calculation**|The subcategory for the VAT Statement.<br><br/> Select a subcategory here if the **Category** field displays **Calculation**.|  
    |**Optional**|Select to indicate that the XML element that is represented by the category code isn't required in the electronic VAT declaration.|  

1. Choose the **OK** button.  

You can now map the VAT statement data directly to an XML element.  

## Related information

- [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
- [Setting Up Electronic VAT and ICP Declarations](how-to-set-up-electronic-vat-and-icp-declarations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
