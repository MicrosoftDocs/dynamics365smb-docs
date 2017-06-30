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
# How to: Create Electronic Documents for EHF
When you sell goods or services to a customer in the public sector, you must submit documents electronically. In ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/how-to-set-up-customers-for-ehf.md).  
  
 Electronic documents can only be created after a document has been posted or issued. The following procedures describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same steps also apply to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  
  
> [!NOTE]  
>  The sum of lines in an exported electronic document will not reflect invoice rounding, even if it is enabled. Instead, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> sums the lines without rounding.  
  
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
  
    -   **Bill-to Customer**  
  
    -   **Shipment Date**  
  
     Select the **E-Invoice** check box.  
  
     The default value of the **Shipment Date** field is the posting date of the document.  
  
    > [!NOTE]  
    >  For reminders and finance charge memos, the **GLN No.**, **Account Code**, and **E-Invoice** fields are on the **Posting** FastTab.  
  
5.  On the **Home** tab, in the **Posting** group, choose **Post** to post the invoice.  
  
### To create an electronic sales invoice  
  
1.  In the **Search** box, enter **Posted Sales Invoices**, and then choose the related link.  
  
2.  Select the relevant sales invoice.  
  
3.  On the **Home** tab, in the **Invoice** group, choose **Create Electronic Invoice**.  
  
    > [!IMPORTANT]  
    >  The **E-Invoice** check box must be selected on the invoice in order to create an electronic invoice.  
  
4.  Optionally, in the **Create Electronic Invoices** batch job window, set additional filters.  
  
5.  Choose the **OK** button.  
  
 An XML file is created and stored at the location that was defined in the **\($ N\_459 Sales & Receivables Setup $\)** window. You can now submit the document to the customer.  
  
## See Also  
 [EHF Electronic Invoicing in Norway](../ehf-electronic-invoicing-in-norway.md)   
 [\($ T\_311 Sales & Receivables Setup $\)](../\($%20T_311%20Sales%20&%20Receivables%20Setup%20$\).md)   
 [\($ N\_459 Sales & Receivables Setup $\)-duplicate](../-$-n_459-sales-receivables-setup-$-duplicate.md)   
 Create Electronic Credit Memos   
 Create Electronic Invoices   
 Create Electronic Reminders   
 Create Elec. Service Cr. Memos   
 Create Elec. Fin. Chrg. Memos   
 Create Elec. Service Invoices