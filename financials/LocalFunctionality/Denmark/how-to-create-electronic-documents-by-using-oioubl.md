---
    title: Create Electronic Documents in an OIOUBL format | Microsoft Docs
    description: When you sell goods or services to a customer in the Danish public sector, you must submit documents electronically. This topic describes how to do that.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 01/04/2018
    ms.author: bholtorf

---
# How to: Create Electronic Documents in an OIOUBL Format
When you sell goods or services to a customer in the public sector, you must submit sales documents to the customer electronically in an Offentlig Information Online - Universal Business Language format. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], the OIOUBL extension makes it easy to do that for sales and service invoices, credit memos, and reminders (which include finance charge memos). For more information, see [The OIOUBL Extension for Electronic Invoicing in Denmark](ui-extensions-oioubl.md).

You can create an electronic document after you post the sales or service document. The following sections describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same procedure applies to sales and service credit memos and reminders.  

## To post a sales invoice  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoices**, and then choose the related link.  
2.  Open the sales invoice that you want to post.  
3.  Make sure that the **External Document No.** field contains the document number that the customer supplied. OIOUBL electronic documents require this number.
  
    > [!Note]  
    > For service documents, you must fill in the **Your Reference** field.  
  
4.  On the **Invoicing** FastTab, fill in the **EAN No.**, **Account Code**, and **Payment Channel** fields.  

    For reminders and finance charge memos, the fields are on the **Posting** FastTab.  

5.  Post the invoice.  

## To create an electronic sales invoice  
After you post a document, you can create an electronic invoice in an OIOUBL format. The following steps describe the process for posted sales invoices, but the process is the same for other documents.

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Invoices**, and then choose the related link.  
2.  Open the relevant posted sales invoice.  
3.  Choose the **Create Electronic <*document type*>** action.  
4.  Optionally, in the **Create Electronic <*document type*>** window, set additional filters, and then choose the **OK** button.  

An XML file is created and stored at the location that was defined in the **Sales & Receivables Setup** window. You can now submit the document to the customer.  

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[How to: Set Up the OIOUBL Extension](how-to-set-up-oioubl.md)  
[The OIOUBL Extension for Electronic Invoicing in Denmark](ui-extensions-oioubl.md)  

