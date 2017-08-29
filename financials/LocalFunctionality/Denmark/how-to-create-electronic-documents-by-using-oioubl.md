---
    title: How to Create Electronic Documents by Using OIOUBL | Microsoft Docs
    description: When you sell goods or services to a customer in the public sector, you must submit documents electronically. In ADD INCLUDE<!--[!INCLUDE[navnow](includes/how-to-set-up-customers-for-oioubl.md).
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
# How to: Create Electronic Documents by Using OIOUBL
When you sell goods or services to a customer in the public sector, you must submit documents electronically. In ADD INCLUDE<!--[!INCLUDE[navnow](includes/how-to-set-up-customers-for-oioubl.md).  
  
## Creating Electronic Documents  
 Electronic documents can only be created after a document has been posted or issued. The following sections describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same procedure applies to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  
  
#### To post a sales invoice  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoices**, and then choose the related link.  
  
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
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Invoices**, and then choose the related link.  
  
2.  Open the relevant posted sales invoice.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Create Electronic Invoice**.  
  
4.  Optionally, in the **Create Electronic Invoices** window, set additional filters, and then choose the **OK** button.  
  
 An XML file is created and stored at the location that was defined in the **Sales & Receivables Setup** window. You can now submit the document to the customer.  
  
## See Also  
 [How to: Set Up OIOUBL](how-to-set-up-oioubl.md)   
 [How to: Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)   
 [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)   
 Create Electronic Invoices   
 Create Electronic Credit Memos   
 Create Electronic Reminders   
 Create Elec. Fin. Chrg. Memos   
 Create Electronic Service Invoices   
 Create Electronic Service Credit Memo