---
title: "How to: Create Contract Service Credit Memos"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales credit memos, contracts"
  - "service contracts, creating sales credit memos"
  - "contract service credit memos, setting up"
  - "contracts, creating sales credit memos"
ms.assetid: c0cb74e0-c546-412e-acad-ab0847cb03c2
caps.latest.revision: 8
ms.author: "edupont"
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
# How to: Create Contract Service Credit Memos
You can use a contract service credit memo when a customer cancels a prepaid service contract or removes a service item from a prepaid contract. You can also use it to correct an erroneous service invoice.  
  
### To create a contract service credit memo  
  
1.  In the **Search** box, enter **Service Credit Memos**, and then choose the related link.  
  
2.  Create a new service credit memo.  
  
3.  Fill in the **No.** field.  
  
4.  In the **Customer No.** field, enter the number of the customer in the service contract.  
  
     On the **Invoicing** FastTab, you can see information copied from the **Customer** card. If you want to post the credit memo to a different customer than the one specified on the **General** FastTab, enter the number of that customer in the **Bill\-to Customer No.** field.  
  
    > [!NOTE]  
    >  You can compare the credit memo to the original posted document in the **Posted Service Invoices** window. In the **Search** box, enter **Posted Service Invoices**, and then choose the related link.  
  
5.  On the **General** FastTab, in the **Posting Date** and **Document Date** fields, enter a date.  
  
6.  On the credit memo lines, enter information about the items that have been returned or removed, or the allowance that will be sent. You can also choose to use the **Get Prepaid Contract Entries** batch job.  
  
 To automatically create a credit memo when contract lines are removed from a service contract, in the **Service Contract** window, on the **Invoice Details** FastTab, select the **Automatic Credit Memos** check box.  
  
 To manually create a credit memo when contract lines are removed from a service contract, in the **Service Contract** window, on the **Actions** tab, in the **Functions** group, choose **Credit Memo**.  
  
## See Also  
 [How to: Remove Contract Lines](../Service/how-to-remove-contract-lines.md)   
 [How to: Cancel Contracts](../Service/how-to-cancel-contracts.md)   
 Get Prepaid Contract Entries