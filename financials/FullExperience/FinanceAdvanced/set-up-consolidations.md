---
title: "Set Up Consolidations"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "consolidating, setting up"
  - "balance sheets, setting up consolidations"
ms.assetid: ac6a664b-0245-4ccf-a37b-db1f7c7e36bf
caps.latest.revision: 4
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
# Set Up Consolidations
You can consolidate the general ledger entries of two or more separate companies \(subsidiaries\) into a consolidated company. Each individual company involved in a consolidation is called a business unit. The combined company is called the consolidated company. You can import data into the consolidated company from other companies in the same database, from other [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] databases, or from files. You can use any number of business units in a consolidation.  
  
 You can set up the consolidated company in the same way that you set up other companies. The chart of accounts in the consolidated company is independent of the charts of accounts in the business units, and the charts of accounts in individual business units may differ from one another.  
  
 In the chart of accounts for each business unit, indicate which accounts are to be included in the consolidation. If the financial statements of a business unit are in a different currency than those of the consolidated company, fill in the **Consol. Translation Method** field for each of the accounts in the consolidation. Typically, *Average Rate \(Manual\)* or *Historical Rate* is used for income statement accounts, and *Closing Rate* is used for balance sheet accounts.  
  
 In the consolidated company, you can create a business unit card for each of the companies. The business unit card includes information, such as the dates of the business unit's fiscal year, the percentage of each account that should be included in the consolidation, and the version of [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] that the business unit is recorded in.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Specify \- in the subsidiary companies \- which general ledger accounts in each business unit are to be included in the consolidation, and specify the consolidation translation method for each account.|[How to: Enter Consolidation Information on General Ledger Accounts](../Finance/how-to-enter-consolidation-information-on-general-ledger-accounts.md)|  
|Set up—in the consolidated company—a business unit card for each company to be included in the consolidation.|[How to: Enter Basic Information for Consolidated Companies](../Finance/how-to-enter-basic-information-for-consolidated-companies.md)|  
  
## See Also  
 [Consolidate Companies](../Finance/consolidate-companies.md)   
 Consol. Translation Method