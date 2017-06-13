---
title: "How to: Use Allocation Keys in General Journals"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "allocation keys, using in general journal"
ms.assetid: 0678f662-0fa1-4a4d-83c3-ad6b42f197a9
caps.latest.revision: 13
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
# How to: Use Allocation Keys in General Journals
You can allocate an entry in a general journal to several different accounts when you post the journal. The allocation can be made by quantity, percentage, or amount.  
  
### To use allocation keys  
  
1.  In the **Search** box, enter **Recurring General Journal**, and then choose the related link.  
  
2.  In the **Batch Name** field at the top of the window, create a new journal batch.  
  
3.  In the **Name** field, enter a name for the batch, such as **CLEANING**. In the **Description** field, enter a description, such as **Cleaning Expenses Journal**.  
  
4.  When you are done, choose the **OK** button. A new, empty recurring journal opens.  
  
5.  In the **Recurring Method** field, select the preferred method, such as **Variable**. In the **Recurring Frequency** field, enter the appropriate period, **1M**, for example.  
  
6.  Fill in the **Posting Date**, **Document No.**, **Account Type**, **Account No.**, and **Description** fields. Enter the total amount to be allocated in the **Amount** field.  
  
7.  In the last field on the line, press the Enter key to set up the line. Select the line, and then from the **Navigation** tab, in the **Line** group, choose **Allocations**.  
  
8.  Create a line for each allocation. You must fill in either the **Allocation %**, **Allocation Quantity**, or **Amount** field. You must also fill in the **Account No.** field and, if you are allocating the transaction among global dimensions, the global dimension fields.  
  
9. If you enter a percentage on a line, the amount in the **Amount** field is calculated automatically. These amounts have the opposite sign from the total amount in the **Amount** field in the recurring journal.  
  
10. After entering the allocations lines, choose **OK** to return to the **Recurring General Journal** window. The **Allocated Amt. \(LCY\)** field is filled in and matches the **Amount** field.  
  
11. Post the journal.  
  
## See Also  
 [How to: Fill In Recurring Journals](../Finance/how-to-fill-in-recurring-journals.md)   
 [How to: Set Up Multiple Journal Batches](../Finance/how-to-set-up-multiple-journal-batches.md)   
 [General Journal Batches](assetId:///a4aa58bd-0981-4423-850d-ee77f1c772b4)