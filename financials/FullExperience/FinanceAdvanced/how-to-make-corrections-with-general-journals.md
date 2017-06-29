---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Make Corrections with General Journals
When you discover an erroneous entry, it must be corrected. Since it is not possible to change or delete a ledger entry, the only way to correct an error is to post one or more corrective entries. FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> offers two features that can help you correct erroneous postings.  
  
-   Reversing by creating a credit memo. For more information, see [Correction of Incorrect Posted Documents](../Finance/correction-of-incorrect-posted-documents.md).  
  
-   Reversing when you apply customer or vendor ledger entries. For more information, see [How to: Unapply Applied Customer or Vendor Ledger Entries](../Topic/How%20to:%20Unapply%20Applied%20Customer%20or%20Vendor%20Ledger%20Entries.md).  
  
 To correct erroneous entries using the general journal, you must use the **Correction** field.  
  
> [!NOTE]  
>  The **Correction** field is not accessible by default. Use the Page Designer to add the field to the **General Journal** window. This requires permissions to the development environment.  
  
### To correct a ledger entry using a general journal  
  
1.  In the **Search** box, enter **General Journal**, and then choose the related link.  
  
2.  Fill in the first line of the journal with the corrective information. Select the **Correction** field. For more information, see Correction.  
  
3.  Post the journal.  
  
### To view the results of posting  
  
1.  Open the **Chart of Accounts** window.  
  
2.  On the line with the relevant account number, select the amount in the **Net Change** field.  
  
3.  Browse to the last entry on the account \(or whichever entry is relevant\), and on the **Actions** tab, choose **Navigate**.  
  
4.  In the **Navigate** window, on the **Actions** tab, choose **Show** to view the general ledger entries.  
  
> [!NOTE]  
>  The amount in the **Debit Amount** or **Credit Amount** field for the line is negative. The **Debit Amount** and **Credit Amount** fields on the ledger entries are updated differently, depending on whether the entry is a normal or a corrective entry.  
  
## See Also  
 [How to: Fill and Post General Journals](../Finance/how-to-fill-and-post-general-journals.md)   
 [Correction of Incorrect Posted Documents](../Finance/correction-of-incorrect-posted-documents.md)   
 Correction   
 [How to: Reverse Journal Postings](../Finance/how-to-reverse-journal-postings.md)   
 [How to: Reverse Journal Postings](../Finance/how-to-reverse-journal-postings.md)   
 [How to: Unapply Applied Customer or Vendor Ledger Entries](../Topic/How%20to:%20Unapply%20Applied%20Customer%20or%20Vendor%20Ledger%20Entries.md)