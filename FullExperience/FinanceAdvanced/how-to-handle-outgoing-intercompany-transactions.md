---
title: "How to: Handle Outgoing Intercompany Transactions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (documents), handling outgoing transactions"
  - "intercompany (outbox), handling outgoing transactions"
  - "intercompany (journals), handling outgoing transactions"
ms.assetid: 0219693f-a583-4c23-a26b-501d75c03507
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
# How to: Handle Outgoing Intercompany Transactions
When you post an intercompany journal or document, or send an intercompany order confirmation, the transactions are sent to your intercompany outbox. In order for them to be sent on to your intercompany partners, you must open the outbox and process them.  
  
### To handle outgoing intercompany transactions  
  
1.  In the **Search** box, enter **IC Outbox Transactions**, and then choose the related link.  
  
2.  In the **\($ N\_611 IC Outbox Transactions $\)** window, select the transaction. On the **Navigate** tab, in the **Outbox Transactions** group, choose **Details** to see the details of a transaction.  
  
3.  In the **\($ N\_611 IC Outbox Transactions $\)** window, enter an option in the **\($ T\_414\_10 Line Action $\)** field for each transaction.  
  
4.  You can either fill in the field on one line at a time, or you can select several lines. On the **Actions** tab, in the **Functions** group, choose **Set Line Action**, and then choose the relevant option.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Complete Line Actions**, and then choose the **Yes** button in the window that appears.  
  
6.  If any of the lines in the outbox contains **Send to IC Partner** in the **Line Action** field, each line has been sent to the relevant partner's inbox.  
  
7.  If any of the lines contains **Return to Inbox** in the **Line Action** field, they have been moved to the inbox. You can accept them in the inbox. Documents or journal lines will then be created in your company.  
  
8.  If any of the lines contains **Cancel** in the **Line Action** field, you must now post a correction to the original transaction that you posted in your company.  
  
## See Also  
 [The Intercompany Inbox](../Finance/the-intercompany-inbox.md)   
 [How to: Handle Incoming Intercompany Transactions](../Finance/how-to-handle-incoming-intercompany-transactions.md)   
 [How to: Re\-create Intercompany Inbox and Outbox Transactions](../Finance/how-to-re-create-intercompany-inbox-and-outbox-transactions.md)   
 [\($ T\_414\_10 Line Action $\)](assetId:///248b95e0-52a6-4154-bc5b-ef694e713dfd)