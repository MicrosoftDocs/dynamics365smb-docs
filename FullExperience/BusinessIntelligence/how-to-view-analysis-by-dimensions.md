---
title: "How to: View Analysis by Dimensions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "analysis views (general ledger), viewing"
ms.assetid: 67db6166-de2e-48fd-95d1-45794484838f
caps.latest.revision: 7
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
# How to: View Analysis by Dimensions
You can use the **Analysis by Dimensions** matrix to view the amounts in your general ledger using the analysis views that you have already set up. You fill in the **\($ N\_554 Analysis by Dimensions $\)** window to define what will be shown in the matrix, and then you choose **Show Matrix** to view the matrix.  
  
-   The leftmost columns contain information based on what you have selected in the **Show as Lines** field in the header.  
  
-   The rightmost columns contain information based on to what you have selected in the **Show as Columns** field in the header.  
  
 The columns in the matrix also display the following information.  
  
|**Column**|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|----------------|---------------------------------------|  
|**Code**|Shows the code given to a dimension value.|  
|**Name**|Shows the name given to a dimension value.|  
|**Total Amount**|Shows the total amount for the amount type that you chose in the **[\($ N\_554\_29 Show $\)](assetId:///37df8884-b937-46b7-a3a7-8b902a59b65f)** field on the **Options** tab.|  
|**Matrix**|The remaining columns show amounts based on an analysis view.|  
  
### To view an analysis by dimensions  
  
1.  In the **Search** box, enter **Analysis by Dimensions**, and then choose the related link.  
  
2.  Select the relevant analysis view. On the **Home** tab, in the **Process** group, choose **Edit Analysis View**.  
  
3.  On each FastTab, fill in the fields. [!INCLUDE[bp_fieldhelp]()]  
  
4.  On the **Actions** tab, choose **Show Matrix**.  
  
5.  To see a specification of an amount shown in the matrix window, choose the amount.  
  
> [!IMPORTANT]  
>  You cannot select a period length shorter than the period specified for the date compression on the **Analysis View** card.  
>   
>  The **Next Set** and **Previous Set** commands are inactive if you have selected **Period** in either the **Show as Lines** or **Show as Columns** field.  
  
> [!NOTE]  
>  You can use the **\($ R\_28 Dimensions \- Detail $\)** report to display a detailed classification of how dimensions have been used on entries over a selected period. You can use the **\($ R\_27 Dimensions \- Total $\)** report to display only the total amounts.  
  
> [!TIP]  
>  The **Option** FastTab gives you many different choices to view the amounts according to your needs.  
>   
>  You can also change the view by changing the contents of the **Show as Lines** field and **Show as Columns** field.  
>   
>  To reverse lines and columns, on the **Navigate** tab, choose **Reverse Lines and Columns**.  
  
## See Also  
 [How to: Set Up Analysis Views](../BusinessIntelligence/how-to-set-up-analysis-views.md)   
 [\($ T\_363\_12 Date Compression $\)](assetId:///4b8d801a-7da2-476b-8076-ffadab2597f6)   
 [\($ R\_28 Dimensions \- Details $\)](../Topic/\($%20R_28%20Dimensions%20-%20Details%20$\).md)   
 [\($ R\_27 Dimensions \- Totals $\)](../Topic/\($%20R_27%20Dimensions%20-%20Totals%20$\).md)   
 [How to: Update Analysis Views](../BusinessIntelligence/how-to-update-analysis-views.md)   
 [How to: Set Up Analysis Views](../BusinessIntelligence/how-to-set-up-analysis-views.md)   
 [\($ T\_348 Dimension $\)](assetId:///09a43eac-15fc-4036-9913-fe2b74a18bf3)