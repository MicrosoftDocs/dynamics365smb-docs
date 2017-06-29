---
title: "How to: Apply Answers from the Configuration Questionnaire"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, setup questionnaires"
  - "setup questionnaires, RapidStart Services"
ms.assetid: 406dcd0d-b388-4d99-af28-c207303ec141
caps.latest.revision: 14
ms.author: "edupont"
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
# How to: Apply Answers from the Configuration Questionnaire
After you have imported and validated information from a setup questionnaire, you can transfer, or apply the setup data to the corresponding tables in the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database.  
  
### To apply answers from the setup questionnaire  
  
1.  In the **Search** box, enter **Configuration Questionnaire**, and then choose the related link. The **\($ N\_8610 Setup Questionnaire $\)** window opens.  
  
2.  Select a configuration questionnaire from the list, and on the **Home** tab, choose **Edit List**.  
  
3.  You can apply answers in one of two ways.  
  
     To apply the whole questionnaire, on the **Process** tab, choose **Apply Answers**.  
  
     \-or\-  
  
     To apply answers for a specific **Question Area** only, choose **Question Areas**, select a **Question Area** in the list, and then on the **Home** tab, choose **Edit**. In the **Process** group, choose **Apply Answers**.  
  
### To verify that answers have been applied successfully  
  
1.  Check setup windows for the various functional areas of [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]. To locate the window, in the **Search** box, enter the name of the setup window, and then choose the related link.  
  
     The following table identifies some common setup tables, but your verification of answers depends on which setup tables you use.  
  
    |Area|Search term|  
    |----------|-----------------|  
    |Company Information|Company Information|  
    |Fixed Assets|FA Setup|  
    |General Ledger|General Ledger Setup|  
    |Inventory|Inventory Setup|  
    |Manufacturing|Manufacturing Setup|  
    |Purchases & Payables|Purchases & Payables Setup|  
    |Relationship Management|Marketing Setup|  
    |Service Management|Service Setup|  
    |Sales & Receivables|Sales & Receivables Setup|  
    |Warehouse|Warehouse Setup|  
  
2.  Verify that the fields have been populated with the correct data from the various question areas in the setup questionnaire.  
  
 You have now configured setup with the customer’s business information and rules.  
  
## See Also  
 [Gather Customer Setup Values](../SetupAndAdministration/gather-customer-setup-values.md)