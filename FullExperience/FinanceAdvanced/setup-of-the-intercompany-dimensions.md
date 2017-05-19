---
title: "Setup of the Intercompany Dimensions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (dimensions), setting up"
ms.assetid: eeba9144-ccf2-4a96-83fa-125e875cb351
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
# Setup of the Intercompany Dimensions
If you and your intercompany partners want to be able to exchange transactions with dimensions linked to them, you need to use intercompany dimensions.  
  
 You must agree with your partner companies on the dimensions that all of you will use when you create intercompany transactions. For example, the parent company of the group creates a simplified version of their own set of dimensions, exports these intercompany dimensions into an XML file and distributes it to each of the companies in the group.  
  
 Each of the subsidiaries then imports the XML file into the IC Dimension table and maps the intercompany dimensions to the dimensions in their own Dimension table.  
  
## Parent Company  
 If your company is defining the set of intercompany dimensions that your group will use as a common reference, follow the procedure: [How to: Define Intercompany Dimensions](../Finance/how-to-define-intercompany-dimensions.md).  
  
## Subsidiary Company  
 If your company has received an XML file containing the IC dimensions that your group will use as a common reference, follow the procedure: [How to: Import Intercompany Dimensions](../Finance/how-to-import-intercompany-dimensions.md).  
  
## All Companies  
 Once you have defined or imported the intercompany dimensions, you need to associate each of the IC dimensions with one of your company's dimensions, and vice versa. In the IC Dimensions window, you specify how IC dimensions on incoming transactions will be translated into dimensions from your company's Dimension table. In the Dimension window, you specify how your dimensions will be translated into intercompany dimensions on outgoing transactions. Follow the procedure: [How to: Map Intercompany Dimensions to Your Company’s Dimensions](../Finance/how-to-map-intercompany-dimensions-to-your-company’s-dimensions.md).  
  
## See Also  
 [How to: Set Up Intercompany Postings](../Finance/how-to-set-up-intercompany-postings.md)   
 [Setup of the Intercompany Chart of Accounts](../Finance/setup-of-the-intercompany-chart-of-accounts.md)   
 [About Intercompany Postings](../Finance/about-intercompany-postings.md)