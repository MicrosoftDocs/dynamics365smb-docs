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
# How to: Renumber Document Numbers in Journals
To make sure that you do not receive posting errors because of the document number order, you can use the **Renumber Document Numbers** function before you post a journal.  
  
 In all journals that are based on the general journal, the **Document No.** field is editable so that you can specify different document numbers for different journal lines or the same document number for related journal lines.  
  
 If the **No. Series** field on the journal batch is filled, then the posting function in general journals requires that the document number on individual or grouped journal lines be in sequential order. To make sure that you do not receive posting errors because of the document number order, you can use the **Renumber Document Numbers** function before you post the journal. If related journal lines were grouped by document number before you used the function, they will remain grouped but may be assigned a different document number.  
  
 This function also works on filtered views.  
  
 Any renumbering of document numbers will respect related applications, such as a payment application that has been made from the document on the journal line to a vendor account. Accordingly, the **Applies\-to ID** and **Applies\-to Doc. No.** fields on the affected ledger entries may be updated.  
  
> [!NOTE]  
>  The following procedure is based on the **General Journal** window, but applies to all other journals that are based on the general journal, such as the **Payment Journal** window.  
  
### To renumber document numbers  
  
1.  In the **Search** box, enter **General Journals**, and then choose the related link.  
  
2.  When you are ready to post the journal, on the **Actions** tab, in the **Functions** group, choose **Renumber Document Numbers**.  
  
 Values in the **Document No.** field are changed, where required, so that the document number on individual or grouped journal lines are in sequential order. After documents are renumbered, you can proceed to post the journal.  
  
## See Also  
 No. Series   
 Document No.   
 General Journal   
 [Work with General Journals](../Finance/work-with-general-journals.md)