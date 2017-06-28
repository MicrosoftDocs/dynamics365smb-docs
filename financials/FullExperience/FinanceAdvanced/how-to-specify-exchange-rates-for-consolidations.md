---
title: "How to: Specify Exchange Rates for Consolidations"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "exchange rates, specifying for consolidations"
  - "consolidating, specifying exchange rates"
ms.assetid: 7cacbf03-ee70-4bf4-8f28-b0f091a9dce9
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
# How to: Specify Exchange Rates for Consolidations
There are three exchange rates that [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] uses when consolidating the financial statements of business units if the financial statements are in a foreign currency. They are:  Average Rate \(Manual\), Closing Rate and Last Closing Rate. Typically, Average Rate \(Manual\) is used for income statement accounts, and Closing Rate is used for balance sheet accounts. The chart of accounts in the business unit's company specifies which rate is used for which accounts.  
  
 If the **Currency Exchange Rate Table** field on the business unit card contains Local, you can change the exchange rate from the business unit card. The exchange rates are copied from the **Currency Exchange Rate** table, but you can change them before consolidating. Before you can enter the exchange rates, you must enter information about the relevant business unit.  
  
 For more information, see [How to: Enter Basic Information for Consolidated Companies](../Finance/how-to-enter-basic-information-for-consolidated-companies.md).  
  
### To specify exchange rates for consolidations  
  
1.  In the **Search** box, enter **Business Units**, and then choose the related link.  
  
2.  In the **\($ N\_240 Business Units $\)** window, select the line with the relevant business unit. On the **Navigate** tab, in the **Exch. Rates** group, choose **Average Rate \(Manual\)**.  
  
3.  In the **Change Exchange Rate** window, the contents of the **Relational Exch. Rate** field have been copied from the **Currency Exchange Rate** table, but you can modify them. Close the window.  
  
4.  In the **Search** box, enter **Business Units**, and then choose the related link.  
  
5.  On the **Navigate** tab, in the **Exch. Rates** group, choose **Closing Rate**.  
  
6.  Modify the contents of the **Relational Exch. Rate** field as appropriate.  
  
## See Also  
 [How to: Process Consolidations](../Finance/how-to-process-consolidations.md)   
 [How to: Adjust Currency Exchange Rates](../Finance/how-to-adjust-currency-exchange-rates.md)