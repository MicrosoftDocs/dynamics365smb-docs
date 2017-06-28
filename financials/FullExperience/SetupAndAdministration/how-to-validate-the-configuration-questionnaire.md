---
title: "How to: Validate the Configuration Questionnaire"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "setup questionnaires, validating"
  - "RapidStart Services, setup questionnaires"
ms.assetid: 2002c933-d8ec-4598-a898-8eba5332de3c
caps.latest.revision: 19
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
# How to: Validate the Configuration Questionnaire
It is important to validate the setup questionnaire before you apply it to the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database. Validation is a manual review process to make sure that the fields have been entered in the correct [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] format. It is also a way to make sure that data formatting is preserved during the import from Excel.  
  
 A common validation task is to check that text strings are not entered into date fields. This review process is necessary because the format of the answer in the questionnaire is not validated automatically when the **Apply Answers** function is run.  
  
> [!NOTE]  
>  In general, validation of the setup questionnaire is a manual process only. However, there are checks for regional formatting inconsistencies. In addition, you will have errors if the structure of your [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database does not match the structure of the migration database.  
  
### To validate the setup questionnaire  
  
1.  In the **Configuration Questionnaire** window, select the questionnaire you want. On the **Home** tab, in the **Process** group, choose **Question Areas**.  
  
2.  Select a **Question Area** and choose **Edit**.  
  
3.  For each question, validate that the value in the **\($ T\_8612\_6 Answer $\)** field corresponds to the format provided in the **\($ T\_8612\_5 Answer Option $\)** field. For example, validate that the address of a company is in text format.  
  
4.  If you find errors, you can troubleshoot and make corrections in Excel by exporting the questionnaire, and then importing it again. Alternatively, you can also correct errors directly in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] as you review the answers in the **\($ N\_8613 Question Areas $\)** window.  
  
5.  Repeat these steps for each **Question Area**.  
  
 After you have completed your validation, your data is ready to be applied to the database.  
  
## See Also  
 [How to: Apply Answers from the Configuration Questionnaire](../SetupAndAdministration/how-to-apply-answers-from-the-configuration-questionnaire.md)