---
title: "How to: Map Intercompany Dimensions to Your Company’s Dimensions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (dimensions), mapping"
ms.assetid: 1c61f7f2-d816-4fd9-9c4a-9dbcd247f245
caps.latest.revision: 10
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
# How to: Map Intercompany Dimensions to Your Company’s Dimensions
After you fill in the **IC Dimensions** window with the dimensions that you and your intercompany partners have agreed to use, you have to associate each of the intercompany dimensions with one of your company's dimensions, and vice versa. In the **IC Dimensions** window, you specify how IC dimensions on incoming transactions will be translated into dimensions from your company's Dimension table. In the **Dimension** window, you specify how your dimensions will be translated into intercompany dimensions on outgoing transactions.  
  
 If any of the intercompany dimensions have the same code as the corresponding dimensions in your company's Dimension table, then you can have the program automatically map the dimensions:  
  
### To map intercompany dimensions to your company's dimensions  
  
1.  In the **Search** box, enter **IC Dimensions**, and then choose the related link.  
  
2.  In the **IC Dimensions** window, select the lines that you want to automatically map.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Map to Dim. with Same Code**. The IC dimension values will be mapped automatically at the same time.  
  
4.  For each intercompany dimension that is not mapped automatically, fill in the **Map\-to Dimension Code** field.  
  
5.  On the **Navigate** tab, in the **IC Dimensions** group, choose **IC Dimension Values**.  
  
6.  In the **IC Dimension Values** window, fill in the **Map\-to Dimension Value Code** field for each IC dimension value.  
  
7.  In the **Search** box, enter **Dimensions**, and then choose the related link.  
  
8.  In the **Dimensions** window, select the lines that you want to automatically map.  
  
9. On the **Actions** tab, in the **Functions** group, choose **Map to IC Dim. with Same Code**.  
  
10. For each intercompany dimension that is not mapped automatically, fill in the **Map\-to IC Dimension Value Code** field.  
  
    > [!IMPORTANT]  
    >  This field is available in the **Dimensions** window, but it is not shown by default. [!INCLUDE[bp_customize](../Finance/includes/bp_customize_md.md)]  
  
11. On the **Navigate** tab, in the **Dimension** group, choose **Dimension Values**.  
  
12. In the **Dimension Values** window, fill in the **Map\-to IC Dimension Value Code** field for each dimension value.  
  
## See Also  
 [Setup of the Intercompany Dimensions](../Finance/setup-of-the-intercompany-dimensions.md)   
 [How to: Define Intercompany Dimensions](../Finance/how-to-define-intercompany-dimensions.md)   
 [How to: Import Intercompany Dimensions](../Finance/how-to-import-intercompany-dimensions.md)   
 [IC Dimensions](assetId:///8516c2fd-f6ad-457d-b9d5-3cd95a728401)   
 [IC Dimension Values](assetId:///c5ce1fd7-c3d3-44e1-b668-b2aeabfc77d1)   
 [Map\-to IC Dimension Value Code](assetId:///b4967177-3629-45e1-8096-0cffb3527c1b)