---
title: "Tips and Tricks: RapidStart Services"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "migrating, transactions"
  - "transactions, migrating"
  - "troubleshooting, RapidStart Services"
  - "RapidStart Services, troubleshooting"
ms.assetid: f98afded-f986-409c-9c83-07dbba94e753
caps.latest.revision: 10
ms.author: "jswymer"
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
# Tips and Tricks: RapidStart Services
When you configure companies using ADD INCLUDE<!--[!INCLUDE[rimlong](../SetupAndAdministration/includes/rimlong_md.md)]-->, there are some tips and tricks that you can take advantage of to help your implementation go smoothly.  
  
## Take advantage of configuration templates  
 Configuration templates can help you streamline your implementation process. By using them, you can include similar customers in segments and then develop an implementation protocol that treats all customers in a segment in a similar manner. In that way, you can apply a level of preconfiguration to each segment and continue with a rapid implementation.  
  
## Configuration questionnaires  
 To aid the process of filling out a configuration questionnaire, consider defining default answers to indicate best practices.  
  
## Batch creation of journal lines  
 We recommend that you use the data migration tools provided to migrate journal entries. Otherwise, if you use a batch job to create journal lines, that has a limited scope and only generates pre\-default fields into a journal. The rest of the journal then has to be completed manually.  
  
## Migrating transactions  
 We recommend that you migrate opening balances in steps, in the following order.  
  
1.  Migrate general ledger opening balances without using the general ledger account subledgers. Use specific opening balance offsetting accounts, one set up for each subledger. Set up the offsetting accounts to enable direct postings.  
  
2.  Migrate open customer ledger entries.  
  
3.  Migrate open item ledger entries.  
  
4.  Migrate open fixed asset entries.  
  
## See Also  
 [Set Up a Company With RapidStart Services for Microsoft Dynamics NAV](../SetupAndAdministration/set-up-a-company-with-rapidstart-services-for-microsoft-dynamics-nav.md)