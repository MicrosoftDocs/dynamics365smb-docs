---
title: "How to: Reverse Journal Postings"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "journal postings"
  - "erroneous entries, reversing journal postings"
  - "ledger entries, deleting"
  - "deleting, journal postings"
  - "ledger entries, reversing"
  - "entries, reversing"
  - "posting, reverse journals"
  - "correcting, journal postings"
  - "reversing, journal postings"
ms.assetid: a184af83-d880-49cd-a5e7-4a4af9d2c522
caps.latest.revision: 12
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
# How to: Reverse Journal Postings
To undo an erroneous journal posting, select the entry and create a reverse  entry \(entries identical to the original entry but with opposite sign in the amount field\) with the same document number and posting date as the original entry. After reversing an entry, you must make the correct entry.  
  
 You can only reverse entries posted from a general journal line. An entry can be reversed only once, either alone or as part of a whole register. After you have reversed an entry from a register, you can no longer reverse the whole register, but must reverse any other transactions individually.  
  
 You can reverse entries from the following windows:  
  
-   [General Ledger Entries](DynamicsNAV:////runpage?Page=20)  
  
-   [Customer Ledger Entries](DynamicsNAV:////runpage?Page=25)  
  
-   [Vendor Ledger Entries](DynamicsNAV:////runpage?Page=29)  
  
-   [Bank Account Ledger Entries](DynamicsNAV:////runpage?Page=372)  
  
-   [FA Ledger Entries](DynamicsNAV:////runpage?Page=5604)  
  
-   [Maintenance Ledger Entries](DynamicsNAV:////runpage?Page=5641)  
  
-   [G\/L Registers](DynamicsNAV:////runpage?Page=116)  
  
### To reverse a journal posting  
  
1.  Open the relevant window.  
  
2.  Select the entry that you want to reverse.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Reverse Transaction**.  
  
4.  In the **G\/L Registers** window, select the relevant register.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Reverse Register**.  
  
6.  You can change the description in the **Description** field.  
  
7.  On the **Actions** tab, in the **Reversing** group, choose **Reverse**.  
  
> [!IMPORTANT]  
>  Before you can reverse an applied customer or vendor ledger entry, you must unapply the entry.  
>   
>  You can only reverse entries generated from a general journal line.  
>   
>  The following entries cannot be reversed:  
>   
>  -   Bank account ledger entries that are closed or linked to a check ledger entry.  
> -   VAT ledger entries that are closed.  
> -   Journal ledger entries from an unbalanced transaction.  
> -   Fixed assets ledger entries where the fixed asset has been sold.  
> -   Fixed assets ledger entries, if the reversal results in a negative book value.  
> -   Entries that have been date compressed.  
  
## See Also  
 [How to: Unapply Applied Customer or Vendor Ledger Entries](../Topic/How%20to:%20Unapply%20Applied%20Customer%20or%20Vendor%20Ledger%20Entries.md)   
 [How to: Make Corrections with General Journals](../Finance/how-to-make-corrections-with-general-journals.md)   
 [How to: Unapply Applied Customer or Vendor Ledger Entries](../Topic/How%20to:%20Unapply%20Applied%20Customer%20or%20Vendor%20Ledger%20Entries.md)