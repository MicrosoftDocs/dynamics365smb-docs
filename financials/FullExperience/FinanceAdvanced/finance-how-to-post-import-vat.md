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
# How to: Post Import VAT
After you have set up codes for import VAT, you can post import VAT invoices.  
  
### To post import VAT  
  
1.  In the **Search** box, enter **General Journal**, and then choose the related link.  
  
2.  In the **General Journal** window, fill in one line in the journal with the amount of the invoice and the general ledger account for import VAT.  
  
3.  In the **Gen. Posting Type** field, enter **Purchase**.  
  
4.  In the **VAT Bus. Posting Group** field, select the posting group that you entered in the import VAT combination in the **VAT Posting Setup** window.  
  
5.  In the **VAT Prod. Posting Group** field, select the posting group thaaat you set up for import VAT. You have to do this only if the general ledger account does not have these codes assigned.  
  
    > [!IMPORTANT]  
    >  These fields may not be shown by default. ADD INCLUDE<!--[!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]-->  
  
6.  After filling in the fields, on the **Home** tab, choose **Post** to post the journal.  
  
## See Also  
 [How to: Set Up Codes for Import VAT](../how-to-set-up-codes-for-import-vat.md)   
 [How to: Record VAT](../how-to-record-vat.md)   
 [How to: Post Import VAT with Purchase Invoices](../how-to-post-import-vat-with-purchase-invoices.md)   
 [How to: View VAT Entries](../how-to-view-vat-entries.md)