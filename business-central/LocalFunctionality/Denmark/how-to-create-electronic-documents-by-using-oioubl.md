---
    title: Create Electronic Documents in an OIOUBL format | Microsoft Docs
    description: When you sell goods or services to a customer in the Danish public sector, you must submit documents electronically. This topic describes how to do that.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Create Electronic Documents by Using OIOUBL
When you sell goods or services to a customer in the public sector, you must submit documents electronically. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can create electronic documents for invoices, credit memos, reminders, and finance charge memos. Before you can create the electronic documents, you must have set up file locations and information about the customers. For more information, see [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md).  

You can create an electronic document after you post the sales or service document. The following sections describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same procedure applies to sales and service credit memos and reminders.  

## To post a sales invoice  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoices**, and then choose the related link.  
2.  Open the sales invoice that you want to post.  
3.  Make sure that the **External Document No.** field contains the document number that the customer supplied. OIOUBL electronic documents require this number.

    > [!Note]  
    > For service documents, you must fill in the **Your Reference** field.  

4.  On the **Invoicing** FastTab, fill in the **GLN** and **OIOUBL Account Code** fields.  

    For reminders and finance charge memos, the fields are on the **Posting** FastTab.  

5.  Post the invoice.  

## To create an electronic sales invoice  
After you post a document, you can create an electronic invoice in an OIOUBL format. The following steps describe the process for posted sales invoices, but the process is the same for other documents.

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Invoices**, and then choose the related link.  
2.  Open the relevant posted sales invoice.  
3.  Choose the **Create Electronic <*document type*>** action.  
4.  Optionally, in the **Create Electronic <*document type*>** page, set additional filters, and then choose the **OK** button.  

This generates an XML file that is stored at the default download location on your device.


> [!Note]
> With the online version of Business Central, the XML file is automatically created in the Download folder on the pc.

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
 [Set Up OIOUBL](how-to-set-up-oioubl.md)   
 [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)   
 [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)
