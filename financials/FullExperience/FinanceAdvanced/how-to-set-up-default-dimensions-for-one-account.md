---
title: "How to: Set Up Default Dimensions for One Account"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "dimensions, setting up default"
  - "default dimensions, setting up for one account"
  - "default, dimensions"
ms.assetid: 84419bae-3185-46d7-9349-c02ca8b45f1f
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
# How to: Set Up Default Dimensions for One Account
You can set up a default dimension for a specific individual account. ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> will then copy this code to the journal, sales, or purchase line when the account number field is filled in on the line. However, you may delete or change the code if appropriate.  
  
 The following procedure is for setting up default dimension for a customer account.  
  
### To set up default dimensions for one account  
  
1.  In the **Search** box, enter **Customers** , and then choose the related link.  
  
2.  On the **Navigate** tab, in the **Customer** group, choose **Dimensions**.  
  
3.  Fill in a line for each new default dimension you want to set up. For Help about a specific field, click the field and press **F1**.  
  
> [!WARNING]  
>  If an account is used in the **Adjust Exchange Rates** batch job or the **Post Inventory Cost to G\/L** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  
  
> [!IMPORTANT]  
>  Entering a code in the dimension field on the account card does not guarantee that the code will be used when you post. This is because it may be changed on the journal, sales, or purchase line. To make sure that that the code is not changed when you post, select the **Same Code** option.  
  
## See Also  
 [How to: Set Up Default or Required Dimensions for Account Types](../Finance/how-to-set-up-default-or-required-dimensions-for-account-types.md)   
 [How to: Set Up Global Dimensions](../Finance/how-to-set-up-global-dimensions.md)   
 [How to: Set Up Shortcut Dimensions](../Finance/how-to-set-up-shortcut-dimensions.md)   
 Default Dimension   
 Dimension   
 Adjust Exchange Rates   
 Post Inventory Cost to G\-L