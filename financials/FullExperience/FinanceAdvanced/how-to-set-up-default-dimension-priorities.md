---
title: "How to: Set Up Default Dimension Priorities"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "dimensions, setting up priorities"
  - "dimensions, setting up default"
  - "default dimensions, setting up priorities"
ms.assetid: 4dc06e3a-eda5-4a0c-847f-0305e3a6a906
caps.latest.revision: 6
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
# How to: Set Up Default Dimension Priorities
Different account types, such as a customer account and an item account, can have different default dimensions set up. As a result, an entry can have more than one default dimension proposed for a dimension. To avoid such conflicts, you can apply priority rules to the different sources.  
  
### To set up default dimension priorities  
  
1.  In the **Search** box, enter **Default Dimension Priorities**, and then choose the related link.  
  
2.  In the **Default Dimension Priorities** window, in the **Source Code** field, enter the source code for the entry table to which default dimension priorities will apply.  
  
3.  Fill in a line for each default dimension priority that you want for the selected source code. For Help about a specific field, choose the field and press F1.  
  
4.  Repeat the procedure for each source code for which you want to set up default dimension priorities.  
  
> [!IMPORTANT]  
>  If you set up two tables with the same priority for the same source code, ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> will always select the table with the lowest table ID.  
  
## See Also  
 [How to: Set Up Default Dimensions for One Account](../Finance/how-to-set-up-default-dimensions-for-one-account.md)   
 Default Dimension   
 Dimension