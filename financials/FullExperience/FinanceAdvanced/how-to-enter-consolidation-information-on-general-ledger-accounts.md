---
title: "How to: Enter Consolidation Information on General Ledger Accounts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "consolidating, general ledger accounts"
ms.assetid: f161b986-e765-4b02-8e06-8d9240001181
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
# How to: Enter Consolidation Information on General Ledger Accounts
After setting up the chart of accounts for a consolidated company, you must specify accounts for consolidation. In each company that will be included in the consolidation, for each general ledger account, you must specify the general ledger account in the consolidated company to which the balance will be transferred on consolidation.  
  
### To enter consolidation information on general ledger accounts  
  
1.  On the Application menu ![Microsoft Dynamics NAV Application menu](../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/media/rtc_applicationmenu.png "RTC\_ApplicationMenu"), choose **Select Company** to open the company for a business unit.  
  
2.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
3.  In the **Chart of Accounts** window, for each general ledger account that has the **Posting** type, fill in the **Consol. Debit Acc.**, **Consol. Credit Acc.**, and **Consol. Translation Method** fields. FIX INCLUDE HERE<!--[!INCLUDE[bp_fieldhelp]()] -->  
  
    > [!IMPORTANT]  
    >  These fields are available in the Chart of Accounts window, but not shown by default. FIX INCLUDE HERE<!--[!INCLUDE[bp_customize](../Finance/includes/bp_customize_md.md)] -->  
  
4.  After entering account numbers for all the general ledger accounts, close the **Chart of Accounts** window.  
  
 If you have more than one business unit in the same database, close the current company, open another business unit ,and repeat the procedure.  
  
## See Also  
 [How to: Process Consolidations](../Finance/how-to-process-consolidations.md)   
 Chart of Accounts