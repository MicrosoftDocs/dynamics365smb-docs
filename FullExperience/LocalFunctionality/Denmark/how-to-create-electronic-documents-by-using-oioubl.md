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
When you sell goods or services to a customer in the public sector, you must submit documents electronically. In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can create electronic documents for invoices, credit memos, reminders, and finance charge memos. Before you can create the electronic documents, you must have set up file locations and information about the customers. For more information, see [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md) and [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md).  
  
## Creating Electronic Documents  
 Electronic documents can only be created after a document has been posted or issued. The following sections describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same procedure applies to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  
  
#### To post a sales invoice  
  
1.  In the **Search** box, enter **Sales Invoices**, and then choose the related link.  
  
2.  Open the sales invoice that you want to post.  
  
3.  On the **General** FastTab, make sure that the **\($ T\_36\_100 External Document No. $\)** field contains the document number that the customer supplied.  
  
    > [!IMPORTANT]  
    >  This is required if you want to create an electronic invoice.  
  
     For service documents, you must fill in the **\($ T\_36\_11 Your Reference $\)** field on the **General** FastTab.  
  
4.  On the **Invoicing** FastTab, make sure that the following fields have values:  
  
    -   **\($ T\_36\_13600 EAN No. $\)**  
  
    -   **\($ T\_36\_13602 Account Code $\)**  
  
    -   **\($ T\_36\_13620 Payment Channel $\)**  
  
     For reminders and finance charge memos, the fields are on the **Posting** FastTab.  
  
5.  Post the invoice.  
  
#### To create an electronic sales invoice  
  
1.  In the **Search** box, enter **Posted Sales Invoices**, and then choose the related link.  
  
2.  Open the relevant posted sales invoice.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Create Electronic Invoice**.  
  
4.  Optionally, in the **\($ B\_13600 Create Electronic Invoices $\)** window, set additional filters, and then choose the **OK** button.  
  
 An XML file is created and stored at the location that was defined in the **\($ N\_459 Sales & Receivables Setup $\)** window. You can now submit the document to the customer.  
  
## See Also  
 [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md)   
 [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md)   
 [OIOUBL Electronic Invoicing Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/oioubl-electronic-invoicing-overview.md)   
 [\($ B\_13600 Create Electronic Invoices $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-b_13600-create-electronic-invoices-$-.md)   
 [\($ B\_13601 Create Electronic Credit Memos $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-b_13601-create-electronic-credit-memos-$-.md)   
 [\($ B\_13602 Create Electronic Reminders $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-b_13602-create-electronic-reminders-$-.md)   
 [\($ B\_13603 Create Elec. Fin. Chrg. Memos $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-b_13603-create-elec.-fin.-chrg.-memos-$-.md)   
 [\($ B\_13604 Create Electronic Service Invoices $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-b_13604-create-electronic-service-invoices-$-.md)   
 [\($ B\_13605 Create Electronic Service Credit Memo $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-b_13605-create-electronic-service-credit-memo-$-.md)