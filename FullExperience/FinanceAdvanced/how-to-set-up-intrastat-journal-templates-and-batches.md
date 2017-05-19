---
title: "How to: Set Up Intrastat Journal Templates and Batches"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Intrastat, setting up batches"
  - "templates, Intrastat"
  - "Intrastat, batches"
  - "Intrastat, journal templates"
  - "Intrastat, setting up templates"
ms.assetid: 0fe39776-88ee-41cd-a8ee-c980bcbb5a59
caps.latest.revision: 12
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
# How to: Set Up Intrastat Journal Templates and Batches
Before you can use the **Intrastat Journal**, you must decide which Intrastat journal templates and batches you will use. You do this in the **\($ N\_325 Intrastat Journal Templates $\)** and **\($ N\_327 Intrastat Jnl. Batches $\)** windows.  
  
 Because Intrastat is reported monthly, you must create 12 Intrastat journals based on the same template. You set up the names of these 12 journals in the **\($ N\_327 Intrastat Jnl. Batches $\)** window.  
  
### To set up Intrastat templates  
  
1.  In the **Search** box, enter **Intrastat Journal Templates**, and then choose the related link.  
  
2.  In the **\($ N\_325 Intrastat Journal Templates $\)** window, create several templates if you need several different forms.  
  
3.  Assign a **Name** and **Description** to each template.  
  
### To set up Intrastat batches  
  
1.  Select the template for which you want to create batches. On the **Navigate**, in the **Template** group, choose **Batches**.  
  
2.  Enter a **Name** and **Description** for each batch.  
  
    > [!NOTE]  
    >  We recommended that you set up a unique **Intrastat Journal Batch** for each month.  
  
3.  On each batch line, set up the relevant information in the following fields.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_262\_14 Statistics Period $\)**|Enter the statistics period as a four\-digit number, where the first two digits represent the year and the next two digits represent the month. For example, enter **1206** for June 2012.|  
    |**\($ T\_262\_16 Currency Identifier $\)**|Enter a code that identifies the currency of the Intrastat report. For example, you can enter **EUR** for euro and **USD** for US dollars.|  
    |**\($ T\_262\_15 Amounts in Add. Currency $\)**|Select this field if you want the Intrastat report to display in the additional reporting currency.|  
    |**\($ T\_262\_13 Reported $\)**|This field is automatically filled when you run the **\($ B\_593 Intrastat \- Make Disk Tax Auth $\)** batch job. If you want to run the batch job again, clear this field.|  
  
> [!NOTE]  
>  **Intrastat Journal Batches** are not similar in structure to other journal batches.  
  
## See Also  
 [How to: Fill In Intrastat Journals](../Finance/how-to-fill-in-intrastat-journals.md)   
 [How to: Reorganize Intrastat Journals](../Finance/how-to-reorganize-intrastat-journals.md)   
 [\($ N\_325 Intrastat Journal Templates $\)](assetId:///e2493625-337b-42ec-9f25-085e8d4d0d69)   
 [\($ N\_327 Intrastat Jnl. Batches $\)](assetId:///25c8dbbd-5742-4ece-b494-c7e24b25541e)   
 [\($ T\_262\_15 Amounts in Add. Currency $\)](assetId:///3859cfbd-f61b-4541-a07b-dee7bb57bdda)   
 [\($ B\_593 Intrastat \- Make Disk Tax Auth $\)](../Topic/\($%20B_593%20Intrastat%20-%20Make%20Disk%20Tax%20Auth%20$\).md)