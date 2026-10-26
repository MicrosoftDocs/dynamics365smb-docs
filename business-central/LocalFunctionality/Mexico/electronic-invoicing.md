---
title: Electronic Invoicing in the Mexican Version
description: Learn how to set up, stamp, send, and cancel CFDI electronic invoices and customer payment receipts in the Mexican version of Business Central.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: CFDI, CFDI support, export sales invoice, export service invoice, credit memos, electronic documents, digital signature
ms.search.form: 10458, 10459, 27001, 27002, 27003, 27010,27011, 27011, 27012, 27013,27014,27015, 27016, 27017, 27018, 27040, 27041, 27042, 27043, 27044
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Electronic invoicing in the Mexican version

Mexican companies must be able to send invoices electronically as Comprobante Fiscal Digital por Internet (CFDI) files. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports CFDI so that you can export sales and service invoices and credit memos as electronic documents that have the required digital signature.

> [!NOTE]
> [!INCLUDE[prod_short](../../includes/prod_short.md)] generates CFDI 4.0 documents. Customer payment receipts use the Pagos 2.0 complement, and Carta de Porte documents use the 3.1 complement.

The CFDI file is an XML file that contains:  

- Name of issuing company
- Fiscal address of issuing company
- Tax scheme of the issuing company  
- Federal tax registration number (RFC) of issuing company
- RFC of the receiving company  
- Quantity and description of the goods or services  
- Unit price
- Tax amounts listed by tax type  
- Currency code
- Customs location, which includes the date and number of the customs document, if the transaction is an import.
- Digital stamp of the issuing company, which the tax authorities (SAT) assign.
- Digital stamp of an authorized service provider, PAC, that you choose.  

> [!IMPORTANT]  
> You need to submit the electronic invoices to a PAC, which is an authorized service provider appointed by the Mexican tax authorities (SAT). SAT certified more than one PAC in Mexico, and you must obtain the appropriate information to communicate with the PAC of your choice. By default, [!INCLUDE [prod_short](../../includes/prod_short.md)] supports integration with [Interfactura](https://interfactura.com/), but you can use another PAC of your choice.  

## Get started

Before you can use [!INCLUDE[prod_short](../../includes/prod_short.md)] for electronic invoicing, obtain the required SAT certificate and PAC service information. Upload the certificate to [!INCLUDE[prod_short](../../includes/prod_short.md)] and select it on **General Ledger Setup**. Learn more in [Set up electronic invoicing](how-to-set-up-electronic-invoicing.md). The [Servicio de Administración Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website provides information about SAT certificates and keys.

You can use different SAT certificates for company branches. In addition to the SAT certificate you specify on the **General Ledger Setup** page, you can assign a separate SAT certificate for each location associated with a company branch. To use this feature, you must enable the **Multiple SAT Certificates** option on the **General Ledger Setup** page:

- If the option isn't enabled, the certificate from the **General Ledger Setup** page is used to sign all electronic documents.
- If the option is enabled, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses the **SAT Certificate** assigned to the document's location. If the location doesn't have a certificate, it uses the certificate from **General Ledger Setup**.
- For transfer shipments, the certificate is determined by the **Transfer-From Code** location.
- When multiple certificates are enabled, **SAT Certificate Name** and **SAT Certificate Source** on the posted document card show the certificate selected for the document.

> [!TIP]
> Use the **Set up Mexican CFDI information** assisted setup guide to map information about your company and how you use [!INCLUDE [prod_short](../../includes/prod_short.md)] to the various fields in the CFDI files.

You must also specify the web services that you use to communicate with the PAC to obtain digital stamps. Learn more in [Set up PAC Web Services](how-to-set-up-pac-web-services.md).

> [!IMPORTANT]  
> SAT certified more than one PAC in Mexico, and you must obtain the appropriate information to communicate with the PAC of your choice.  

You must also specify information about your company and each of your customers and vendors. Learn more in [Set up electronic invoicing](how-to-set-up-electronic-invoicing.md).  

## Send electronic documents

When you post an invoice or credit memo, you can send it to your customer. But first you must obtain a digital stamp from the PAC. [!INCLUDE[prod_short](../../includes/prod_short.md)] communicates with the PAC through web services to request a stamp, and your company and the PAC digitally sign the document automatically.  

Electronic invoices and credit memos are sent from the email account assigned to the **Default** email scenario. The recipient is the email address on the **Customer Card** for the bill-to customer. On **General Ledger Setup**, select **Send PDF Report** to attach a PDF in addition to the XML file.

> [!IMPORTANT]  
> Configure the email account before you send documents. The electronic invoicing workflow uses the configured email connector, so SMTP isn't the only option. Learn more in [Set up email](../../admin-how-setup-email.md).

If you also want to print the documents, the documents include a Quick Response (QR) bar code and other information that identifies the related electronic invoice. This information makes the printed document computer-readable and provides a link between the electronic document and the printed document. To learn about generating electronic invoices, refer to [Generate Electronic Invoices](how-to-generate-electronic-invoices.md).  

## Cancel documents

You might have to revert a transaction, such as if you have to change the location of a shipment for some reason. You might also have to send such cancellations as electronic documents.  

When you request cancellation, fill in **CFDI Cancellation Reason Code**. Fill in **Substitution Document No.** when the selected cancellation reason requires a replacement document.

The following table describes the cancellation reasons:

|Option   |Description  |
|---------|-------------|
|01     |Voucher issued with errors in relation.|
|02     |Voucher issued with unrelated errors.|
|03     |The operation wasn't carried out.|
|04     |Related nominative operation in a global invoice.|

If you choose code *01*, then you must also specify the document that substitutes the canceled document in the **Substitution Document No.** field.  

### Send a posted sales invoice for cancellation

1. Open the posted sales invoice that you want to cancel. In the **Electronic Document** action group, select **Cancel**.
1. Select **Cancel Request** and confirm. This action allows you to send the cancellation request to the PAC service and receive a cancellation ID for the document.  

After a successful response, **Electronic Document Status** changes to **Cancel In Progress**, and the response supplies the **CFDI Cancellation ID**. If the PAC rejects the request, the status changes to **Cancel Error**. Review **Error Code** and **Error Description**. These responses don't replace the original **Date/Time Stamped**.

### Send a request to update the status

The SAT authorities need to process and approve the document that you need to cancel. The information about the status should be requested from the PAC service.  

In the **Electronic Document** action group, select **Cancel**, and then select **Get Response** to check the cancellation status. The document must have a **CFDI Cancellation ID** and a status of **Cancel In Progress** or **Cancel Error**.

> [!NOTE]  
> The possible responses **EnProceso**, **Rechazado**, and **Cancelado** update the **Electronic Document Status** field for the next values respectively: **Cancel In Progress**, **Cancel Error**, or **Canceled**.

### Manually cancel a posted sales invoice

For a document with **Electronic Document Status** set to **Cancel In Progress** or **Cancel Error**, select **Cancel** in the **Electronic Document** action group. Then select **Mark as Canceled** to update its status manually.

> [!IMPORTANT]
> **Mark as Canceled** only changes the document's status in [!INCLUDE[prod_short](../../includes/prod_short.md)]. It doesn't submit a cancellation request to the PAC or reverse the posted accounting entries. Confirm the cancellation with your PAC or SAT before you use this action.

### Schedule cancellation status checks

Use a job queue entry to run codeunit **10151 E-Invoice Cancel Request Batch**. The batch checks records that have a **CFDI Cancellation ID** and an **Electronic Document Status** of **Cancel Error** or **Cancel In Progress**. It covers posted sales invoices, sales credit memos, sales shipments, transfer shipments, and customer ledger entries.

> [!IMPORTANT]
> Review **Cancel on Time Expiration** on **General Ledger Setup** before scheduling the batch. When this option is enabled, the batch can also mark eligible documents as canceled after 72 hours. A status change in [!INCLUDE[prod_short](../../includes/prod_short.md)] isn't confirmation that SAT approved the cancellation.

## Communication component

The electronic invoicing functionality handles communication with PAC web services and generates the QR codes included in printed documents. On-premises deployments use the `Microsoft.Dynamics.NAV.MX.dll` library for communication and signing. Online deployments use a separate service implementation.

When you generate an electronic document to request a stamp, [!INCLUDE[prod_short](../../includes/prod_short.md)] creates an XML document and sends it to the PAC for processing. The original XML document contains the same information as the original string field that is shown on the printed document. The original string includes the following information:  

- Document date  
- Document type  
- Payment terms  
- Name, address, and federal registration number of your company  
- Name, address, and federal registration number of the customer  
- Line amounts and quantities  

The PAC returns an XML document that has the original string, but this file also includes a section for the digital stamp. In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can export the XML files for documents that have a digital stamp and learn more about the data that goes into each XML element.  

## Related information

[Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
[Set Up PAC Web Services](how-to-set-up-pac-web-services.md)  
[Generate Electronic Invoices](how-to-generate-electronic-invoices.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
