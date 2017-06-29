---
title: "How to: Set Up XBRL Lines"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "eXtensible Business Reporting Language, setting up lines"
  - "taxonomies, setting up"
ms.assetid: f2c16ef0-afcf-4031-a56c-6fb8b36f78bb
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
# How to: Set Up XBRL Lines
After you import or update the taxonomy, the lines of the schemas must be supplied with all the information that is required. This information will include basic company information, the actual financial statements, notes to the financial statements, supplemental schedules, and other information that is required to satisfy the particular financial reporting requirements.  
  
 You set up the XBRL Lines by mapping the data in the taxonomy to the data in your general ledger.  
  
### To set up XBRL lines  
  
1.  In the **Search** box, enter **XBRL Taxonomies**, and then choose the related link.  
  
2.  In the **XBRL Taxonomies** window, select a taxonomy from the list.  
  
3.  On the **Home** tab, in the **Process** group, choose **Lines**.  
  
4.  Select a line and fill in the fields. ADD INCLUDE<!--[!INCLUDE[bp_fieldhelp]()]-->  
  
5.  To read detailed information about what to fill in, on the **Navigate**, in the **XBRL Line** group, choose **Information**.  
  
6.  To set up the mapping of the general ledger accounts in the chart of accounts to the XBRL lines, on the **Navigate**, in the **XBRL Line** group, choose **G\/L Map Lines**.  
  
7.  To add notes to the financial statement, on the **Navigate**, in the **XBRL Line** group, choose **Notes**.  
  
> [!NOTE]  
>  You can only export data that correspond to the source type you have selected in the **Source Type** field that includes description and notes.  
  
> [!NOTE]  
>  Lines that are not relevant can be marked as line type **NOT APPLICABLE** so the lines are not exported.  
  
## See Also  
 [How to: Import XBRLTaxonomies](../BusinessIntelligence/how-to-import-xbrltaxonomies.md)   
 [How to: Update XBRL Taxonomies](../BusinessIntelligence/how-to-update-xbrl-taxonomies.md)   
 XBRL Export Instance \- Spec. 2   
 [eXtensible Business Reporting Language](../BusinessIntelligence/extensible-business-reporting-language.md)