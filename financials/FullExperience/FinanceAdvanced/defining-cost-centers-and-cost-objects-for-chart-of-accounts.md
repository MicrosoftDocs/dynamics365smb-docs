---
title: "Defining Cost Centers and Cost Objects for Chart of Accounts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, defining chart of accounts"
ms.assetid: 8c2c0be4-45ac-4683-84e9-ce632309bad1
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
# Defining Cost Centers and Cost Objects for Chart of Accounts
You can automatically transfer the expense and income entries from the general ledger to cost accounting either for each general ledger posting or with a batch job. When you do the transfer, ADD INCLUDE<!--[!INCLUDE[navnowlong](../ApplicationDesign/includes/navnowlong_md.md)]--> only transfers the entries that are already linked to a cost center or a cost object. To establish a meaningful transfer, you must ensure that the cost centers and cost objects are correctly defined.  
  
## Defining Default Dimension Values for General Ledger Accounts  
 For each general ledger account, you can define default dimension values in the **Default Dimension** table. The following example shows how to define that there should always be a DEPARTMENT cost center, but never be a PROJECT cost object when posting to a general ledger account.  
  
|**Dimension Code**|**Value Posting**|  
|------------------------------------------|-----------------------------------------|  
|Department|Code Mandatory|  
|Project|No Code|  
  
## Defining Dimension Values for Overhead Costs and Direct Costs  
 You can transfer overhead costs to a cost center and direct costs to a cost object. The following table shows the optimal combination of the dimension setup values.  
  
|Transfer To|Cost Center Posting|Cost Object Posting|  
|-----------------|-------------------------|-------------------------|  
|Cost Center|Code Mandatory|No Code|  
|Cost Object|No Code|Code Mandatory|  
  
> [!NOTE]  
>  To make sure that the predefined cost center and cost object that you set up in the general ledger are automatically carried over to cost accounting, select the **Check G\/L Postings** check box in the Cost Accounting Setup window.  
  
## See Also  
 [How to: Set Up Cost Centers](../Finance/how-to-set-up-cost-centers.md)   
 [How to: Set Up Cost Objects](../Finance/how-to-set-up-cost-objects.md)   
 Cost Accounting Setup   
 Dimension