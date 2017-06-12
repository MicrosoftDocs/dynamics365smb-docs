---
title: "How to: Create SEPA Direct Debit Collection Entries and Export to a Bank File"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: f774e057-d5e1-4b8e-ac56-8ee1b106f310
caps.latest.revision: 6
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
# How to: Create SEPA Direct Debit Collection Entries and Export to a Bank File
To instruct the bank to transfer the payment amount from the customer’s bank account to your company’s account, you create a direct\-debit collection, which holds information about the customer’s bank account, the affected sales invoices, and the direct\-debit mandate. From the resulting direct\-debit collection entry, you then export an XML file that you send or upload to your electronic bank for processing. Any payments that could not be processed by the bank will be communicated to you by your bank, and you must then manually reject the direct debit\-collection entries in question.  
  
> [!NOTE]  
>  To collect payments using SEPA Direct Debit, the currency on the sales invoice must be EURO.  
  
### To create a direct\-debit collection  
  
1.  In the **Search** box, enter **Direct Debit Collections**, and then choose the related link.  
  
2.  In the **Direct Debit Collections** window, on the **Home** tab, in the **New** group, choose **Create Direct Debit Collection**.  
  
3.  In the **Create Direct Debit Collection** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**From Due Date**|Specify the earliest payment due date on sales invoices that you want to create a direct\-debit collection for.|  
    |**To Due Date**|Specify the latest payment due date on sales invoices that you want to create a direct\-debit collection for.|  
    |**Partner Type**|Specify if the direct\-debit collection is made for customers of type **Company** or **Person**.|  
    |**Only Customers With Valid Mandate**|Specify if a direct\-debit collection is created for customers who have a valid direct\-debit mandate. **Note:**  A direct\-debit collection is created even if the **Direct Debit Mandate ID** field is not filled on the sales invoice.|  
    |**Only Invoices With Valid Mandate**|Specify if a direct\-debit collection is only created for sales invoices if a valid direct\-debit mandate is selected in the **Direct Debit Mandate ID** field on the sales invoice.|  
    |**Bank Account No.**|Specify which of your company’s bank accounts the collected payment will be transferred to from the customer’s bank account.|  
    |**Bank Account Name**|Specifies the name of the bank account that you select in the **Bank Account No.** field. This field is filled automatically.|  
  
4.  Choose the **OK** button.  
  
     A direct\-debit collection is added to the **Direct Debit Collections** window, and one or more direct\-debit collection entries are created.  
  
### To export a direct\-debit collection entry to a bank file  
  
1.  In the **Direct Debit Collections** window, on the **Home** tab, in the **Process** group, choose **Direct Debit Collect. Entries**.  
  
2.  In the **Direct Debit Collect. Entries** window, select the entry that you want to export, and then, on the **Home** tab, in the **Process** group, choose **Create Direct Debit** File.  
  
3.  Save the export file to the location from where you send or upload it to your electronic bank.  
  
     In the **Direct Debit Collect. Entries** window, the **Direct Debit Collection Status** field is changed to File Created. In the **SEPA Direct Debit Mandates** window, the **Debit Counter** field is updated with one count.  
  
 If the exported file cannot be processed, for example because the customer is insolvent, you can reject the direct\-debit collection entry. If the exported file is successfully processed by the bank, the due payments of the involved sales invoices are automatically collected from the involved customers. In that case you can close the collection.  
  
### To reject a direct\-debit collection entry  
  
-   In the **Direct Debit Collect. Entries** window, select the entry that was not successfully processed, and then, on the **Home** tab, in the **Process** group, choose **Reject Entry**.  
  
     The value in the **Status** field in the **Direct Debit Collect. Entries** window is changed to **Rejected**.  
  
### To close a direct\-debit collection  
  
-   In the **Direct Debit Collect. Entries** window, select the entry that was successfully processed, and then, on the **Home** tab, in the **Process** group, choose **Close Collection**.  
  
     The related direct\-debit collection is closed.  
  
 You can now proceed to post receipts of payment for the involved sales invoices. You can do this as you typically post payment receipts, such as in the **Payment Registration** window, or you can post the related payment receipts directly from the **Direct Debit Collect. Entries** window. For more information, see [How to: Post SEPA Direct Debit Payment Receipts](../Finance/how-to-post-sepa-direct-debit-payment-receipts.md).  
  
## See Also  
 [Create Direct Debit Collection](../Topic/\($%20R_1200%20Create%20Direct%20Debit%20Collection%20$\).md)   
 [Direct Debit Mandate ID](../Topic/\($%20T_172_8%20Direct%20Debit%20Mandate%20ID%20$\).md)   
 [Direct Debit Collections](../Topic/\($%20N_1207%20Direct%20Debit%20Collections%20$\).md)   
 [Direct Debit Collect. Entries](../Topic/\($%20N_1208%20Direct%20Debit%20Collect.%20Entries%20$\).md)   
 [How to: Set Up SEPA Direct Debit](../BusinessFunctionality/DataExchange/how-to-set-up-sepa-direct-debit.md)   
 [How to: Post SEPA Direct Debit Payment Receipts](../Finance/how-to-post-sepa-direct-debit-payment-receipts.md)   
 [Collect Payments with SEPA Direct Debit](../Finance/collect-payments-with-sepa-direct-debit.md)   
 [Payment Registration](assetId:///491fd4a2-b6a9-4dc7-8e97-7dcb4dd5cae5)