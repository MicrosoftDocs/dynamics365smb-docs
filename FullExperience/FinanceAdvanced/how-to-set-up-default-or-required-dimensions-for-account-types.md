---
title: "How to: Set Up Default or Required Dimensions for Account Types"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "dimensions, setting up required"
  - "dimensions, setting up default"
  - "default dimensions, setting up account types"
ms.assetid: 0f72049c-5908-4066-98c1-592d0905d57a
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
# How to: Set Up Default or Required Dimensions for Account Types
You can set up a default dimension for an account type. [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] will then copy this code to the journal, sales or purchase line when the account type is filled in on the line. However, you may delete or change the code if appropriate.  
  
 You can also make a dimension required, so that it is not possible to post an entry with a specific type of account unless the account has a dimension value assigned to it.  
  
### To set up default or required dimensions for an account type  
  
1.  In the **Search** box, enter **Dimensions**, and then choose the related link.  
  
2.  In the **\($ N\_536 Dimensions $\)** window, select the dimension.  
  
3.  On the **Navigate** tab, in the **Dimension** group, choose **Account Type Default Dim**.  
  
4.  Fill in a line for each new default dimension that you want to set up. [!INCLUDE[bp_fieldhelp]()]  
  
> [!TIP]  
>  If you want to make a dimension required but you do not want to assign a default value to the dimension, leave the **Dimension Value Code** field blank and then select **Code Mandatory** in the **Value Posting** field.  
  
> [!WARNING]  
>  If an account is used in the **\($ B\_595 Adjust Exchange Rates $\)** batch job or the **\($ B\_1002 Post Inventory Cost to G\/L $\)** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  
  
> [!NOTE]  
>  If an account must have a different dimension assigned to it than the default dimension already set up for the account type, you must set up a default dimension for this account. The default dimension for the individual account then replaces the default dimension for the account type.  
  
## See Also  
 [How to: Set Up Dimension Combinations](../Finance/how-to-set-up-dimension-combinations.md)   
 [How to: Set Up Default Dimensions for One Account](../Finance/how-to-set-up-default-dimensions-for-one-account.md)   
 [How to: Set Up Global Dimensions](../Finance/how-to-set-up-global-dimensions.md)   
 [How to: Set Up Shortcut Dimensions](../Finance/how-to-set-up-shortcut-dimensions.md)   
 [\($ T\_352 Default Dimension $\)](assetId:///bd021a4a-f67d-44ca-9e6a-4b54cf91e710)   
 [\($ T\_348 Dimension $\)](assetId:///09a43eac-15fc-4036-9913-fe2b74a18bf3)   
 [\($ B\_595 Adjust Exchange Rates $\)](../Topic/\($%20B_595%20Adjust%20Exchange%20Rates%20$\).md)   
 [\($ B\_1002 Post Inventory Cost to G\-L $\)](../Topic/\($%20B_1002%20Post%20Inventory%20Cost%20to%20G-L%20$\).md)