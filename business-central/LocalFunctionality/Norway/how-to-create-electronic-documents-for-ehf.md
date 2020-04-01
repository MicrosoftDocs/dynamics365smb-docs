---
    title: How to Create Electronic Documents for EHF
    description: When you sell goods or services to a customer in the public sector, you must submit documents electronically.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create Electronic Documents for EHF
When you sell goods or services to a customer in the public sector, you must submit documents electronically.  In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can create electronic documents for invoices, credit memos, reminders, and finance charge memos. Before you can create the electronic documents, you must have set up file locations and information about the customers. For more information, see [Set Up EHF](how-to-set-up-ehf.md) and [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md).

Electronic documents can only be created after a document has been posted or issued. The following procedures describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same steps also apply to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  

> [!NOTE]  
>  The sum of lines in an exported electronic document will not reflect invoice rounding, even if it is enabled. Instead, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] sums the lines without rounding.  

## To post a sales invoice  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoices**, and then choose the related link.  
2.  Select the sales invoice that you want to post, and then choose the **Edit** action.  
3.  On the **General** FastTab, make sure that the following fields contain values:  

    - **External Document No.**  
    - **Your Reference**  

    The **External Document No.** field contains the document number that the customer provided.  

4.  On the **Invoicing** FastTab, make sure that the following fields have values:  

    - **GLN No.**  
    - **Account Code**  
    - **Bill-to Customer**  
    - **Shipment Date**  

    Select the **E-Invoice** check box.  

    The default value of the **Shipment Date** field is the posting date of the document.  

    > [!NOTE]  
    >  For reminders and finance charge memos, the **GLN No.**, **Account Code**, and **E-Invoice** fields are on the **Posting** FastTab.  

5.  Choose the **Post** action to post the invoice.  

## To create an electronic sales invoice  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Invoices**, and then choose the related link.  
2.  Select the relevant sales invoice.  
3.  Choose the **Create Electronic Invoice** action.  

    > [!IMPORTANT]  
    >  The **E-Invoice** check box must be selected on the invoice in order to create an electronic invoice.  

4.  Optionally, in the **Create Electronic Invoices** batch job page, set additional filters.  
5.  Choose the **OK** button.  

An XML file is created and stored at the location that was defined on the **Sales & Receivables Setup** page. You can now submit the document to the customer.  

## See Also  
 [EHF Electronic Invoicing in Norway](ehf-electronic-invoicing-in-norway.md)
