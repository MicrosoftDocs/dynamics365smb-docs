---
title: "How to: Fill In and Post Intercompany Journals"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (journals), filling in and posting"
ms.assetid: cd6b54f1-9537-45f6-bedb-45acb672490e
caps.latest.revision: 11
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
# How to: Fill In and Post Intercompany Journals
Use intercompany \(IC\) journals to post transactions with your intercompany partners. When you post an intercompany journal, a corresponding journal is created in your IC outbox that you can transfer to your partner. Your partner can then post the journal in their company, without having to re\-enter the data.  
  
### To fill in and post an intercompany journal  
  
1.  In the **Search** box, enter **IC General Journal**, and then choose the related link.  
  
2.  In the **Account Type** field, enter either **IC Partner**, **Customer**, or **Vendor**.  In the **Account No.** field, select the IC partner code or the customer or vendor number of the partner that you will send the transaction to.  
  
    > [!NOTE]  
    >  If you enter a customer or vendor number, it must have an IC partner code assigned to it.  
  
3.  Fill in the fields as you would fill in a regular general journal.  
  
4.  In the **IC Partner G\/L Acc. No.** field, enter the IC general ledger account that the amount will be posted to in your partner's company. This field must be filled in on a line with a bank account or general ledger account in either the **Account No.** field or the **Bal. Account No.** field.  
  
5.  After filling in the fields, post the journal.  
  
 Now entries have been posted in your company and corresponding entries have been created in your IC outbox for you to send to your partner company.  
  
## See Also  
 [How to: Set Up Default Intercompany Partner General Ledger Accounts](../Finance/how-to-set-up-default-intercompany-partner-general-ledger-accounts.md)   
 [How to: Handle Incoming Intercompany Transactions](../Finance/how-to-handle-incoming-intercompany-transactions.md)   
 [How to: Handle Outgoing Intercompany Transactions](../Finance/how-to-handle-outgoing-intercompany-transactions.md)   
 [How to: Set Up Intercompany Postings](../Finance/how-to-set-up-intercompany-postings.md)