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
# How to: Receive and Convert Electronic Documents
The generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]-->.  
  
 In addition to receiving electronic documents directly from trading partners, you can receive electronic documents from an OCR service that has turned your PDF or image files into electronic documents. For more information, see [How to: Use OCR to Turn PDF and Image Files into Electronic Documents](../how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md).  
  
 Before you can receive electronic documents through the document exchange service, you must set up various master data, such as company information, vendors, items, and units of measure. These are used to identify the business partners and items when converting data in elements in the incoming document file to fields in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-set-up-a-document-exchange-service.md).  
  
 Before you can receive electronic documents through the OCR service, you must set up and enable the preconfigured service connection. For more information, see [How to: Set Up an OCR Service](../how-to-set-up-an-ocr-service.md).  
  
 The traffic of electronic documents in and out of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-set-up-job-queues.md).  
  
 You can either start the conversion of electronic documents manually, as described in this procedure, or you can enable a workflow to convert electronic documents automatically when they are received. The generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/workflow.md).  
  
> [!NOTE]  
>  When you convert electronic documents received from the OCR service to documents or journal lines in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]-->, multiple lines on the source document will be summed on one line. The single line will be of type G\/L Account and the **Description** and \(G\/L account\) **No.** fields will be empty. The value in the **Amount** field will equal the total amount excluding VAT of all lines in the source document.  
>   
>  To make sure that the **Description** and **No.** fields are filled, you can choose the **Map Text to Account** button in the **Incoming Documents** window to define that a certain invoice text is always mapped to a certain debit or credit account in the general ledger. Going forward, the **Description** field on document or journal lines created from an electronic document for that vendor or customer will be filled with the text in question and the \(G\/L account\) **No.** field with the account in question.  
>   
>  Instead of mapping to a G\/L account, you can also map to a bank account. This is practical, for example, for electronic documents for expenses that are already paid where you want to create a general journal line that is ready to post to a bank account. For more information and examples, see Text-to-Account Mapping Wksh..  
  
 The following procedure describes how to receive a vendor invoice and convert it to a purchase invoice in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]-->. The procedure is the same when you convert a vendor invoice to a general journal line.  
  
### To receive and convert an electronic invoice to a purchase invoice  
  
1.  In the **Search** box, enter **Incoming Documents**, and then choose the related link.  
  
2.  Select the line for the incoming document record that represents a new incoming electronic invoice, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
     In the **Incoming Document Card** window, the related XML file is attached, and most of the fields are prefilled with information from the electronic invoice. For more information, see [How to: Create Incoming Document Records](../how-to-create-incoming-document-records.md).  
  
3.  In the **Data Exchange Type** field, choose **PEPPOL - Invoice** or **OCR – Invoice** depending on the source of the electronic document.  
  
4.  To map text on the vendor invoice to a specific debit account, on the **Actions** tab, in the **General** group, choose **Map Text to Account**, and then fill the **Text-to-Account Mapping Wksh.** window. For more information, see Text-to-Account Mapping Wksh..  
  
5.  On the **Actions** tab, in the **General** group, choose **Create Document**.  
  
     A purchase invoice will be created in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]--> based on the information in the electronic document.  
  
     Any validation errors, typically related to wrong or missing master data in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-handle-errors-when-receiving-electronic-documents.md).  
  
## See Also  
 Incoming Document   
 Text-to-Account Mapping Wksh.   
 OCR Status   
 Status   
 [Incoming Documents](../incoming-documents.md)   
 [How to: Set Up Electronic Document Sending and Receiving](../how-to-set-up-electronic-document-sending-and-receiving.md)   
 [How to: Handle Errors When Receiving Electronic Documents](../how-to-handle-errors-when-receiving-electronic-documents.md)   
 [How to: Send Electronic Documents](../how-to-send-electronic-documents.md)   
 [How to: Set Up Data Exchange Definitions](../how-to-set-up-data-exchange-definitions.md)   
 [Data Exchange](../data-exchange.md)   
 [Business Functionality](../Business%20Functionality.md)