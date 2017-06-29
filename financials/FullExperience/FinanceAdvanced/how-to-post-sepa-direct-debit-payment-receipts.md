---
title: "How to: Post SEPA Direct Debit Payment Receipts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 00efa9e3-054a-4f0f-b2e2-7fce461ec455
caps.latest.revision: 4
ms.author: "sgroespe"
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
# How to: Post SEPA Direct Debit Payment Receipts
When a direct debit collection is successfully processed by your bank, you can proceed to post receipt of the payment for the involved sales invoices. For more information, see [How to: Create SEPA Direct Debit Collection Entries and Export to a Bank File](../BusinessFunctionality/DataExchange/how-to-create-sepa-direct-debit-collection-entries-and-export-to-a-bank-file.md).  
  
 You can post the payment receipt directly from the **Direct Debit Collections** window or the **Direct Debit Collect. Entries** window. Alternatively, you can relay the work to another user by preparing the related journal lines.  
  
### To post a direct\-debit payment receipt from the Direct Debit Collections window  
  
1.  In the **Search** box, enter **Direct Debit Collections**, and then choose the related link.  
  
2.  Select a line for a direct debit collection that has been exported to a bank file and successfully processed by the bank. For more information, see [How to: Create SEPA Direct Debit Collection Entries and Export to a Bank File](../BusinessFunctionality/DataExchange/how-to-create-sepa-direct-debit-collection-entries-and-export-to-a-bank-file.md).  
  
3.  On the **Home** tab, in the **Process** group, choose **Post Payment Receipts**.  
  
4.  In the **Post Direct Debit Collection** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Direct Debit Collection No.**|Specify the direct debit collection that you want to post payment receipt for.|  
    |**General Journal Template**|Specify which general journal template to use for posting the payment receipt, such as the template for cash receipts.|  
    |**General Journal Batch Name**|Specify which general journal batch to use for posting the payment receipt.|  
    |**Create Journal Only**|Select this check box if you do not want to post the payment receipt when you choose the **OK** button. The payment receipt will be prepared in the specified journal and will not be posted until someone posts the journal lines in question.|  
  
5.  Choose the **OK** button.  
  
## See Also  
 Post Direct Debit Collection   
 Direct Debit Collections   
 Direct Debit Collect. Entries   
 [Collect Payments with SEPA Direct Debit](../Finance/collect-payments-with-sepa-direct-debit.md)   
 [Process Incoming Payments](../Finance/process-incoming-payments.md)