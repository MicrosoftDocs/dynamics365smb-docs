---
    title: How to Set Up Electronic Document Sending and Receiving | Microsoft Docs
    description: As an alternative to emailing as file attachments, you can send and receive business documents electronically.
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
# How to: Set Up Electronic Document Sending and Receiving
As an alternative to emailing as file attachments, you can send and receive business documents electronically. By electronic document is meant a standard\-compliant file representing a business document, such as an invoice from a vendor that can be received and converted to a purchase invoice in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The exchange of electronic documents between two trading partners is performed by an external provider of document exchange services. The generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)] supports sending and receiving electronic invoices and credit memos in the PEPPOL format, which is supported by the largest providers of document exchange services. A major provider of document exchange services is preconfigured and ready to be set up for your company.  

 From PDF or image files representing incoming documents, you can have an external OCR service \(Optical Character Recognition\) create electronic documents that you can then convert to document records in [!INCLUDE[d365fin](includes/d365fin_md.md)], like for electronic PEPPOL documents. For example, when you receive an invoice in PDF format from your vendor, you can send it to the OCR service from the **\($ N\_190 Incoming Documents $\)** window. After a few seconds, you receive the file back as an electronic invoice that can be converted to a purchase invoice for the vendor. If you send the file to the OCR service by email, then a new incoming document record is automatically created when you receive the electronic document back.  

 The **PEPPOL** electronic document format is preconfigured to enable you to send electronic invoices and credit memos in the PEPPOL format. First, you must set up various master data, such as company information, customers, items, and units of measure. These are used to identify the business partners and items when converting data in fields in [!INCLUDE[d365fin](includes/d365fin_md.md)] to elements in the outgoing document file. Last, you must select the format in the **\($ N\_366 Electronic Document Format $\)** window for each customer who you will send electronic PEPPOL documents to. For more information, see [How to: Send Electronic Documents](../Topic/How%20to:%20Send%20Electronic%20Documents.md).  

 The **PEPPOL – Invoice** and **PEPPOL – Credit Memo** data exchange definitions are preconfigured to enable you to receive electronic invoices and credit memos in the PEPPOL format. First, you must set up various master data, such as company information, vendors, items, and units of measure. These are used to identify the business partners and items when converting data in elements in the incoming document file to fields in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Last, you must select the data exchange definition in the **\($ N\_190 Incoming Documents $\)** window for each incoming electronic document that you want to convert to a purchase document in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [How to: Receive and Convert Electronic Documents](../Topic/How%20to:%20Receive%20and%20Convert%20Electronic%20Documents.md).  

 The **OCR – Invoice** data exchange definition is preconfigured to enable you to receive electronic documents that are genenrated by the OCR service. To receive, for example, an invoice as an electronic OCR document, you set up master date and then process the document just as when receiving an electronic PEPPOL document. For more information, see [How to: Use OCR to Turn PDF and Image Files into Electronic Documents](../Topic/How%20to:%20Use%20OCR%20to%20Turn%20PDF%20and%20Image%20Files%20into%20Electronic%20Documents.md).  

 The preconfigured services for document exchange and OCR must be enabled before you send or receive. For more information, see [How to: Set Up a Document Exchange Service](../Topic/How%20to:%20Set%20Up%20a%20Document%20Exchange%20Service.md) and [How to: Set Up an OCR Service](../Topic/How%20to:%20Set%20Up%20an%20OCR%20Service.md).  

 The topic contains the following procedures:  

-   To set up the company for electronic document sending and receiving  

-   To set up VAT posting for electronic document sending and receiving  

-   To set up countries\/regions for electronic document sending and receiving  

-   To set up items for electronic document sending and receiving  

-   To set up units of measure for electronic document sending and receiving  

-   To set up customers for electronic document sending  

-   To select the **PEPPOL** electronic document format for electronic document sending  

-   To set up vendors for electronic document receiving  

-   To select the **PEPPOL – Invoice** data exchange definition for electronic document receiving  

-   To set up the G\/L account to use on new purchase invoice lines for non\-identifiable items and non\-items  

### To set up the company for electronic document sending and receiving  

1.  In the **Search** box, enter **Company Information**, and then choose the related link.  

2.  On the **General** FastTab, fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_79\_90 GLN $\)**|Identify your company.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **EndPointID** element under the **AccountingSupplierParty** node in the file. The number is based on the GS1 standard, which is compliant with ISO 6523.|  
    |**\($ T\_79\_19 VAT Registration No. $\)**|Specify your company’s VAT registration number.|  
    |**\($ T\_79\_5700 Responsibility Center $\)**|If your company is set up with a responsibility center, make sure that the **\($ T\_5714\_7 Country\/Region Code $\)** field is filled.|  

### To set up VAT posting for electronic document sending and receiving  

1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  

2.  For each VAT posting setup line that you will use for electronic documents, fill the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_325\_17 Tax Category $\)**|Specify the VAT category.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **TaxApplied** element under the **AccountingSupplierParty** node in the file. The number is based on the UNCL5305 standard.|  

### To set up countries\/regions for electronic document sending and receiving  

1.  In the **Search** box, enter **Country\/Regions**, and then choose the related link.  

2.  For each country\/region that you will exchange electronic documents with, fill the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_9\_10 VAT Scheme $\)**|Identify the national body that issues the VAT registration number for the country\/region in connection with electronic document sending.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **SchemeID** attribute for the **EndPointID** element under both the **AccountingSupplierParty** node and the **AccountingCustomerParty** in the file.<br /><br /> The **\($ T\_9\_10 VAT Scheme $\)** field is only used if the **\($ T\_79\_90 GLN $\)** field in the **\($ N\_1 Company Information $\)** window is not filled. **Note:**  The value in the **\($ T\_9\_1 Code $\)** field in the **\($ N\_10 Countries\/Regions $\)** window must comply with ISO 3166\-1:Alpha2.|  

### To set up items for electronic document sending and receiving  

1.  In the **Search** box, enter **Items**, and then choose the related link.  

2.  For each item that you buy or sell on electronic documents, fill the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_27\_1217 GTIN $\)**|Identifies the item in connection with electronic document sending and receiving. For the PEPPOL format, the field is used as follows:<br /><br /> If the **StandardItemIdentification\/ID** element has the **SchemeID** attribute set to **GTIN**, then the element is mapped to the **\($ T\_27\_1217 GTIN $\)** field on the item card.|  

### To set up units of measure for electronic document sending and receiving  

1.  In the **Search** box, enter **Units of Measure**, and then choose the related link.  

2.  For each unit of measure that you will use for items on electronic documents, fill the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_204\_3 International Standard Code $\)**|Specify the unit of measure code expressed according to the UNECERec20 standard in connection with sending of electronic documents.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **unitCode** attribute of the **InvoicedQuantity** element under the **InvoiceLine** node. **Note:**  If the **\($ T\_37\_13 Unit of Measure $\)** field on the sales line is empty, the UNECERe20 standard value for “Piece” \(H87\) is inserted by default. For more information and a list of valid unit of measure codes, see [Recommendation No. 20 \- Units of Measure used in International Trade](http://www.unece.org/fileadmin/DAM/cefact/recommendations/rec20/rec20_rev3_Annex2e.pdf).|  

### To set up customers for electronic document sending  

1.  In the **Search** box, enter **Customers**, and then choose the related link.  

2.  For each customer who you will send electronic documents to, fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_18\_90 GLN $\)**|Identify the customer.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **EndPointID** element under the **AccountingCustomerParty** node in the file. The number is based on the GS1 standard, which is compliant with ISO 6523.<br /><br /> If the **\($ T\_18\_90 GLN $\)** field is blank, the value in the **\($ T\_18\_86 VAT Registration No. $\)** field is used.|  
    |**\($ T\_18\_86 VAT Registration No. $\)**|Specify the customer's VAT registration number. **Tip:**  Choose the DrillDown button to use the web service that verifies if the number exists in the country’s company register.|  
    |**\($ T\_18\_5700 Responsibility Center $\)**|If the customer is set up with a responsibility center, make sure that the **\($ T\_5714\_7 Country\/Region Code $\)** field is filled.|  

 You can set up each customer with a preferred method of sending business documents, so that you do not have to select a sending option every time that you send a document to the customer. For more information, see [How to: Set Up Document Sending Profiles](../Topic/How%20to:%20Set%20Up%20Document%20Sending%20Profiles.md).  

### To select the PEPPOL electronic document format for electronic document sending  

1.  In the **Search** box, enter **Document Sending Profiles**, and then choose the related link.  

2.  Open an existing document sending profile, or create a new one. For more information, see [How to: Set Up Document Sending Profiles](../Topic/How%20to:%20Set%20Up%20Document%20Sending%20Profiles.md).  

3.  In the **\($ N\_360 Document Sending Profile $\)** window, choose the **\($ T\_60\_21 Electronic Format $\)**, select the line for PEPPOL, and then choose the **OK** button.  

4.  In the **\($ T\_60\_20 Electronic Document $\)** field, select **Yes \(Through Document Exchange Service\)**.  

    > [!NOTE]  
    >  [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically detects if the document is an invoice or a credit memo and applies the PEPPOL format accordingly.  

5.  To make this document sending profile apply to all customers, select the **\($ T\_60\_30 Default $\)** check box on the **General** FastTab. To make it apply to specific customers only, fill the **\($ T\_18\_11 Document Sending Profile $\)** field on the customer cards in question. For more information, see [How to: Set Up Document Sending Profiles](../Topic/How%20to:%20Set%20Up%20Document%20Sending%20Profiles.md).  

 You can now send the electronic document containing the converted data. For more information, see [How to: Send Electronic Documents](../Topic/How%20to:%20Send%20Electronic%20Documents.md).  

### To set up vendors for electronic document receiving  

1.  In the **Search** box, enter **Vendors**, and then choose the related link.  

2.  For each vendor that you will receive electronic documents from, fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_23\_90 GLN $\)**|Identify the vendor.<br /><br /> For example, when you receive electronic invoices in the PEPPOL format, the value in this field is used to populate the **EndPointID** element under the **AccountingSupplierParty** node in the file. The number is based on the GS1 standard, which is compliant with ISO 6523.<br /><br /> If the **\($ T\_23\_90 GLN $\)** field is blank, the value in the **\($ T\_23\_86 VAT Registration No. $\)** field is used.|  
    |**\($ T\_23\_86 VAT Registration No. $\)**|Specify the vendor’s VAT registration number. **Tip:**  Choose the DrillDown button to use the web service that verifies if the number exists in the country’s company register.|  
    |**\($ T\_23\_5700 Responsibility Center $\)**|If the vendor is set up with a responsibility center, make sure that the **\($ T\_5714\_7 Country\/Region Code $\)** field is filled.|  

### To select the PEPPOL \- Invoice data exchange definition for electronic document receiving  

1.  In the **Search** box, enter **Incoming Documents**, and then choose the related link.  

2.  On the line for the electronic document that you want to receive and convert, choose the **\($ T\_130\_30 Data Exchange Type $\)** field, and then select **PEPPOLINVOICE**.  

     If the document to receive is a credit memo, select **PEPPOLCREDITMEMO**.  

 You can now receive the electronic document by starting the data conversion process in the **\($ N\_190 Incoming Documents $\)** window. For more information, see [How to: Receive and Convert Electronic Documents](../Topic/How%20to:%20Receive%20and%20Convert%20Electronic%20Documents.md).  

### To set up the G\/L account to use on new purchase invoice lines for non\-identifiable items and non\-items  

1.  In the **Search** box, enter **Purchases & Payables**, and then choose the related link.  

2.  On the **Data Exchange** FastTab, fill the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_312\_1217 G\/L Account for Non\-Item Lines $\)**|Specifies the G\/L account that is automatically inserted on purchase lines that are created from electronic documents when the incoming document line does not contain an identifiable item. Any incoming document line that does not have a GTIN or the vendor’s item number will be converted to a purchase line of type **G\/L Account**, and the **\($ T\_39\_6 No. $\)** field on the purchase line will contain the account that you select in the **\($ T\_312\_1217 G\/L Account for Non\-Item Lines $\)** field.<br /><br /> If you leave the **\($ T\_312\_1217 G\/L Account for Non\-Item Lines $\)** field blank, and the incoming document has lines without identifiable items, then the purchase document will not be created. An error message will instruct you to fill the **\($ T\_312\_1217 G\/L Account for Non\-Item Lines $\)** field before you can complete the task.|  

## See Also  
 Document Sending Profile   
 Document Sending Profile   
 Electronic Format   
 Electronic Document Format   
 [How to: Set Up Electronic Document Sending and Receiving](../how-to-set-up-electronic-document-sending-and-receiving.md)   
 [Data Exchange](../data-exchange.md)   
 [How to: Send Email Messages](../how-to-send-email-messages.md)   
 [How to: Invoice Sales](../how-to-invoice-sales.md)   
 [How to: Record Purchases](../how-to-record-purchases.md)
