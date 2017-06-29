---
title: "About Mapping"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: d4863ae1-ceea-41c7-b913-8d4bdc02fbf5
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# About Mapping
When you apply data that you have imported from Excel or from a RapidStart package, FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> --> --> --> --> uses the mapping values that you have provided for a particular field and automatically substitutes the values in your data with the values linked to the field. How [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] treats and handles the mapping depends on table relations:  
  
-   If you define a mapping directly for a field in a table, then [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] uses it.  
  
-   If the field has a relation to another table, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] searches for the mapping defined for the primary key field in the related table. The related table, however, must be part of the configuration package.  
  
-   If mapping information is defined in both places, for the field directly and for the primary key in the related table, then [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] will search for the mapping in both places.  
  
-   If the same mappings are defined directly for a field and in the related table, but have different new values, the mapping that is defined directly for the field takes priority over the mapping that is defined for the table that the field is referencing.  
  
## Example  
 The following example illustrates how [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] implements mapping definitions.  
  
1.  Create a configuration table that has a Salesperson\/Purchaser table, table 13. Define a mapping for the Code field. For more information, see [How to: Map Customer Data](../SetupAndAdministration/how-to-map-customer-data.md).  
  
2.  Add additional tables to the package, for example, table 18, Customer, and table 23, Vendor. These tables both reference table 13 through the Salesperson Code and the Purchaser Code, respectively.  
  
3.  When you apply data, the mapping that you provided for the Code field in table 13 will also be considered during the processing of the Salesperson Code and Purchaser Code fields.  
  
## See Also  
 [How to: Map Customer Data](../SetupAndAdministration/how-to-map-customer-data.md)