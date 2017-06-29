---
title: "How to: Create Electronic Documents for EHF"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic documents, creating"
ms.assetid: dfc2fc4c-620a-4893-9fd8-59e49290b05f
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Create Electronic Documents for EHF
When you sell goods or services to a customer in the public sector, you must submit documents electronically. In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can create electronic documents for invoices, credit memos, reminders, and finance charge memos. Before you can create the electronic documents, you must have set up file locations and information about the customers. For more information, see [How to: Set Up EHF](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-ehf.md) and [How to: Set Up Customers for EHF](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-customers-for-ehf.md).  
  
 Electronic documents can only be created after a document has been posted or issued. The following procedures describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same steps also apply to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  
  
> [!NOTE]  
>  The sum of lines in an exported electronic document will not reflect invoice rounding, even if it is enabled. Instead, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] sums the lines without rounding.  
  
### To post a sales invoice  
  
1.  In the **Search** box, enter **Sales Invoices**, and then choose the related link.  
  
2.  Select the sales invoice that you want to post. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, make sure that the following fields contain values:  
  
    -   **External Document No.**  
  
    -   **Your Reference**  
  
     The **External Document No.** field contains the document number that the customer provided.  
  
4.  On the **Invoicing** FastTab, make sure that the following fields have values:  
  
    -   **GLN No.**  
  
    -   **Account Code**  
  
    -   **Bill\-to Customer**  
  
    -   **Shipment Date**  
  
     Select the **E\-Invoice** check box.  
  
     The default value of the **Shipment Date** field is the posting date of the document.  
  
    > [!NOTE]  
    >  For reminders and finance charge memos, the **GLN No.**, **Account Code**, and **E\-Invoice** fields are on the **Posting** FastTab.  
  
5.  On the **Home** tab, in the **Posting** group, choose **Post** to post the invoice.  
  
### To create an electronic sales invoice  
  
1.  In the **Search** box, enter **Posted Sales Invoices**, and then choose the related link.  
  
2.  Select the relevant sales invoice.  
  
3.  On the **Home** tab, in the **Invoice** group, choose **Create Electronic Invoice**.  
  
    > [!IMPORTANT]  
    >  The **E\-Invoice** check box must be selected on the invoice in order to create an electronic invoice.  
  
4.  Optionally, in the **Create Electronic Invoices** batch job window, set additional filters.  
  
5.  Choose the **OK** button.  
  
 An XML file is created and stored at the location that was defined in the **\($ N\_459 Sales & Receivables Setup $\)** window. You can now submit the document to the customer.  
  
## See Also  
 [EHF Electronic Invoicing in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/ehf-electronic-invoicing-in-norway.md)   
 [\($ T\_311 Sales & Receivables Setup $\)](../Topic/\($%20T_311%20Sales%20&%20Receivables%20Setup%20$\).md)   
 [\($ N\_459 Sales & Receivables Setup $\)\-duplicate](../../Sales/-$-n_459-sales-receivables-setup-$-duplicate.md)   
 Create Electronic Credit Memos   
 Create Electronic Invoices   
 Create Electronic Reminders   
 Create Elec. Service Cr. Memos   
 Create Elec. Fin. Chrg. Memos   
 Create Elec. Service Invoices