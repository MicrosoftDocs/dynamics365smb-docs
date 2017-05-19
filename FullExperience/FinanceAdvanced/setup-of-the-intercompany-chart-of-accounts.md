---
title: "Setup of the Intercompany Chart of Accounts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (chart of accounts), setting up"
ms.assetid: 6942285f-f9f0-4db7-8a61-296dff50d920
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
# Setup of the Intercompany Chart of Accounts
Before you and your intercompany partners can begin to transfer intercompany transactions electronically, each of you must set up the intercompany chart of accounts in your company.  
  
 You must agree with your partner companies on the account numbers that all of you will use when you create intercompany transactions. For example, the parent company of the group creates a simplified version of their own chart of accounts, exports this intercompany chart of accounts from their database into an XML file and distributes it to each of the companies in the group.  
  
 Each of the subsidiaries then imports the XML file into the IC Chart of Accounts table and maps the accounts to the accounts in their own chart of accounts.  
  
## Parent Company  
 If your company is defining the intercompany chart of accounts that your group will use as a common reference, follow the procedure: [How to: Define the Intercompany Chart of Accounts](../Finance/how-to-define-the-intercompany-chart-of-accounts.md).  
  
## Subsidiary Company  
 If your company has received an XML file containing the intercompany chart of accounts that your group will use as a common reference, follow the procedure: [How to: Import the Intercompany Chart of Accounts](../Finance/how-to-import-the-intercompany-chart-of-accounts.md).  
  
## All Companies  
 Once you have defined or imported the intercompany chart of accounts, you need to associate each of the IC G\/L accounts with one of your company's G\/L accounts. In the IC Chart of Accounts window, you specify how IC G\/L accounts on incoming transactions will be translated into G\/L accounts from your company's chart of accounts. Follow the procedure: [How to: Map the Intercompany Chart of Accounts to Your Company’s Chart of Accounts](../Finance/how-to-map-the-intercompany-chart-of-accounts-to-your-company’s-chart-of-accounts.md).  
  
## See Also  
 [How to: Set Up Intercompany Postings](../Finance/how-to-set-up-intercompany-postings.md)   
 [Setup of the Intercompany Dimensions](../Finance/setup-of-the-intercompany-dimensions.md)   
 [About Intercompany Postings](../Finance/about-intercompany-postings.md)