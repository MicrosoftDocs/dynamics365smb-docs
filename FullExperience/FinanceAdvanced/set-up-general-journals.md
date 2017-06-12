---
title: "Set Up General Journals"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general journals, setting up"
ms.assetid: 1ca0324a-0c71-410c-85e0-649da5de3c20
caps.latest.revision: 3
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
# Set Up General Journals
General journals are used to post to general ledger accounts and other accounts such as bank, customer, vendor, and fixed assets accounts. Posting with a general journal always creates entries on general ledger accounts. There are other journals besides general journals, such as item transfer journals, physical inventory journals, resource journals and FA journals. These journals do not create entries in the general ledger, but create other types of ledger entries. For example, the physical inventory journal is used to compare the results of a physical inventory count with the quantity on hand calculated by the program. When you post the journal, the program creates a physical inventory ledger entry for every journal line and an item ledger entry for each journal line on which there is a difference between the physical inventory count and the calculated quantity on hand.  
  
 There are several general journal templates, such as the Cash Receipt Journal and the FA G\/L Journal. Each journal template has a separate window with particular functions, and the fields that are needed to support those functions. A number of standard journal templates are set up by default, but you can create new journal templates.  
  
 If you need multiple journals of a certain type, for example a cash receipt journal for each employee in the accounts receivable department, you can create multiple journal batches for a journal template.  
  
 You can assign default balancing accounts to batches that usually use the same balancing account, for example, the cash receipt journal might always use the same cash account. You can also assign reason codes to journal batches or templates.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn about general journal templates.|[Gen. Journal Template](assetId:///eb60bf94-fc5b-442c-acb8-91df074d20d2)|  
|Create multiple journals of the same type.|[How to: Set Up Multiple Journal Batches](../Finance/how-to-set-up-multiple-journal-batches.md)|  
|Assign a default balancing account to a journal batch.|[How to: Set Up Default Balancing Accounts](../Finance/how-to-set-up-default-balancing-accounts.md)|  
|Assign a reason code to appear on all journal entries posted from a journal batch.|[How to: Assign Reason Codes to Journal Batches](../Finance/how-to-assign-reason-codes-to-journal-batches.md)|  
|Assign a reason code to appear on all journal entries posted from a journal template.|[How to: Assign Reason Codes to Journal Templates](../Finance/how-to-assign-reason-codes-to-journal-templates.md)|  
  
## See Also  
 [Work with General Journals](../Finance/work-with-general-journals.md)