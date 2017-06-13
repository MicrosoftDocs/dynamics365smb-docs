---
title: "How to: Set Up Dimension Combinations"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "dimensions, combinations"
ms.assetid: 8f85e0de-fb9e-4d8f-8d82-2a18d8d13756
caps.latest.revision: 8
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
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
# How to: Set Up Dimension Combinations
To avoid posting entries with contradictory or irrelevant dimensions, you can block or limit specific combinations of two dimensions. A blocked dimension combination means that you cannot post both dimensions on the same entry regardless of what the dimension values are. A limited dimension combination lets you post both dimensions to the same entry, but only for certain combinations of dimension values.  
  
### To set up dimension combinations  
  
1.  In the **Search** box, enter **Dimension Combinations**, and then choose the related link.  
  
2.  In the **Dimension Combinations** window, choose the field of the dimension combination and select one of the following options.  
  
    |[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------------------------------|  
    |**No limitation**|This dimension combination has no restrictions. All dimensions values are allowed.|  
    |**Limit**|This dimension combination has restrictions depending on which dimension values that you enter. You must define the limitations in the **Dimension Value Combination** window.|  
    |**Blocked**|This dimension combination is not allowed.|  
  
3.  If you selected the **Limited** option, you must define which combinations of dimension values are blocked. To do this, choose the field to define the dimension combination.  
  
4.  Now select a dimension value combination that is blocked and enter **Blocked** in the field. A blank field means that the dimension value combination is allowed. Repeat if multiple combinations are blocked.  
  
> [!NOTE]  
>  The same dimensions are displayed in both rows and columns and, therefore, all dimension combinations appear two times. [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] automatically displays the setting in both fields. You cannot select anything in the fields from the upper\-left corner and down, because these fields have the same dimension in both rows and columns.  
>   
>  The selected option is not visible before you exit the field.  
>   
>  To show the name of the dimensions instead of the code, select the **Show Column Name** field.  
  
## See Also  
 [How to: Set Up Default Dimensions for One Account](../Finance/how-to-set-up-default-dimensions-for-one-account.md)   
 [Default Dimension](assetId:///bd021a4a-f67d-44ca-9e6a-4b54cf91e710)   
 [Dimension](assetId:///09a43eac-15fc-4036-9913-fe2b74a18bf3)