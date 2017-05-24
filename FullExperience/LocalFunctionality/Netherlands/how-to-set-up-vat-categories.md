---
title: "How to: Set Up VAT Categories"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, categories"
ms.assetid: 1943321d-706b-4be0-9163-369940c379d7
caps.latest.revision: 25
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Set Up VAT Categories
To use the electronic VAT declaration, you must set up a VAT category code for all XML elements in the electronic VAT declaration.  
  
 You must set up all of the possible category and subcategory combinations that represent an XML element in the electronic VAT declaration. Then, you can map the VAT statement data directly to an XML element.  
  
### To set up a VAT category  
  
1.  In the **Search** box, enter **\($ N\_11414 Elec. Tax. Decl. VAT Categories $\)**, and then choose the related link.  
  
2.  In the **\($ N\_11414 Elec. Tax. Decl. VAT Categories $\)** window, on the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique code for each category and subcategory combination. You can enter a maximum of 10 alphanumeric characters.|  
    |**Category**|Specify the main category option for the VAT statement.|  
    |**By Us \(Domestic\)**|The subcategory for the VAT Statement.<br /><br /> Select a subcategory here if the **Category** field displays **By Us \(Domestic\)**.|  
    |**To Us \(Domestic\)**|The subcategory for the VAT Statement.<br /><br /> Select a subcategory here if the **Category** field displays **To Us \(Domestic\)**.|  
    |**By Us \(Foreign\)**|The subcategory for the VAT Statement.<br /><br /> Select a subcategory here if the **Category** field displays **By Us \(Foreign\)**.|  
    |**To Us \(Foreign\)**|The subcategory for the VAT Statement.<br /><br /> Select a subcategory here if the **Category** field displays **To Us \(Foreign\)**.|  
    |**Calculation**|The subcategory for the VAT Statement.<br /><br /> Select a subcategory here if the **Category** field displays **Calculation**.|  
    |**Optional**|Select to indicate that the XML element that is represented by the category code is not required in the electronic VAT declaration.|  
  
4.  Choose the **OK** button.  
  
     You can now map the VAT statement data directly to an XML element.  
  
## See Also  
 [Electronic VAT and ICP Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/electronic-vat-and-icp-declarations.md)   
 [How to: Create Electronic VAT and ICP Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-electronic-vat-and-icp-declarations.md)