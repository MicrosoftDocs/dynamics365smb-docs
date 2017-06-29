---
title: "How to: Create Electronic Documents by Using OIOUBL"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic invoices, creating"
  - "OIOUBL, creating documents"
  - "public sector documents"
ms.assetid: 5f3ccbea-aeb5-4b21-a30f-32db3e56184e
caps.latest.revision: 10
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Create Electronic Documents by Using OIOUBL
When you sell goods or services to a customer in the public sector, you must submit documents electronically. In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can create electronic documents for invoices, credit memos, reminders, and finance charge memos. Before you can create the electronic documents, you must have set up file locations and information about the customers. For more information, see [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md) and [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md).  
  
## Creating Electronic Documents  
 Electronic documents can only be created after a document has been posted or issued. The following sections describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same procedure applies to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  
  
#### To post a sales invoice  
  
1.  In the **Search** box, enter **Sales Invoices**, and then choose the related link.  
  
2.  Open the sales invoice that you want to post.  
  
3.  On the **General** FastTab, make sure that the **External Document No.** field contains the document number that the customer supplied.  
  
    > [!IMPORTANT]  
    >  This is required if you want to create an electronic invoice.  
  
     For service documents, you must fill in the **Your Reference** field on the **General** FastTab.  
  
4.  On the **Invoicing** FastTab, make sure that the following fields have values:  
  
    -   **EAN No.**  
  
    -   **Account Code**  
  
    -   **Payment Channel**  
  
     For reminders and finance charge memos, the fields are on the **Posting** FastTab.  
  
5.  Post the invoice.  
  
#### To create an electronic sales invoice  
  
1.  In the **Search** box, enter **Posted Sales Invoices**, and then choose the related link.  
  
2.  Open the relevant posted sales invoice.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Create Electronic Invoice**.  
  
4.  Optionally, in the **Create Electronic Invoices** window, set additional filters, and then choose the **OK** button.  
  
 An XML file is created and stored at the location that was defined in the **\($ N\_459 Sales & Receivables Setup $\)** window. You can now submit the document to the customer.  
  
## See Also  
 [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md)   
 [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md)   
 [OIOUBL Electronic Invoicing Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/oioubl-electronic-invoicing-overview.md)   
 Create Electronic Invoices   
 Create Electronic Credit Memos   
 Create Electronic Reminders   
 Create Elec. Fin. Chrg. Memos   
 Create Electronic Service Invoices   
 Create Electronic Service Credit Memo