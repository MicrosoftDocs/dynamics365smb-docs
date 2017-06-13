---
title: "How to: Handle Incoming Intercompany Transactions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (inbox), handling incoming"
ms.assetid: d6b76e20-6399-4df8-81b8-d658a46c005b
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
# How to: Handle Incoming Intercompany Transactions
When your intercompany partners send you intercompany transactions, the transactions end up in your intercompany inbox. You must evaluate each transaction in your inbox and act upon it.  
  
### To handle incoming intercompany transactions  
  
1.  In the **Search** box, enter **IC Inbox Transactions**, and then choose the related link.  
  
2.  In the **IC Inbox Transactions** window, to see details of a transaction, select the transaction.  
  
3.  On the **Navigate** tab, in the **Inbox Transactions** group, choose **Details**  
  
4.  In the **IC Inbox Transactions** window, enter an option in the **Line Action** field for each transaction. You can either fill in the field on one line at a time, or you can select several lines and then on the **Actions** tab, in the **Functions** group, choose **Set Line Action**. Choose the relevant option.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Complete Line Actions**.  
  
6.  Fill in the **Complete IC Inbox Action** batch job request page. On the **IC Inbox Transaction** FastTab, you can set filters to determine which transactions will be completed. On the **Options** FastTab, you specify the journal template and batch that you want to use, and other posting details. Choose the **OK** button.  
  
7.  If any of the lines in the inbox contains **Accept** in the **Line Action** field, document or journal lines are created in your company. Open each document or journal, make any necessary changes, and post.  
  
8.  If any of the lines contains **Return to Partner** in the **Line Action** field, they have been moved to the outbox. Send them to your partner from there.  
  
9. If any of the lines contains **Returned by Partner** in the **Transaction Source** field, post a correction to the original transaction that you posted in your company.  
  
## See Also  
 [Line Action](assetId:///9ffc0fbc-0df9-46fa-8120-12197983bd89)   
 [Complete IC Inbox Action](../Topic/\($%20B_511%20Complete%20IC%20Inbox%20Action%20$\).md)   
 [The Intercompany Inbox](../Finance/the-intercompany-inbox.md)   
 [How to: Import Intercompany Transactions from a File](../Finance/how-to-import-intercompany-transactions-from-a-file.md)   
 [How to: Re\-create Intercompany Inbox and Outbox Transactions](../Finance/how-to-re-create-intercompany-inbox-and-outbox-transactions.md)   
 [How to: Handle Outgoing Intercompany Transactions](../Finance/how-to-handle-outgoing-intercompany-transactions.md)