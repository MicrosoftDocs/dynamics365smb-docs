---
title: Electronic invoicing - Mexico
description: Learn how Business Central supports CFDI so that you can export sales and service invoices and credit memos as electronic documents with the required digital signature.
author: brentholtorf
ms.topic: article
ms.search.keywords: CFDI, CFDI support, export sales invoice, export service invoice, credit memos, electronic documents, digital signature
ms.search.form: 10458, 10459, 27001, 27002, 27003, 27010,27011, 27011, 27012, 27013,27014,27015, 27016, 27017, 27018, 27040, 27041, 27042, 27043, 27044
ms.date: 05/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic invoicing in the Mexican version

Mexican companies must be able to send invoices electronically as Comprobante Fiscal Digital por Internet (CFDI) files. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports CFDI so that you can export sales and service invoices and credit memos as electronic documents that have the required digital signature.

> [!NOTE]
> The tax authority (Servicio de Administración Tributaria) announced a version 4.0 of the online digital tax receipt (comprobante fiscal digital por internet—CFDI) system. After the effective date, you can't issue vouchers in versions other than 4.0. Accordingly, [!INCLUDE[prod_short](../../includes/prod_short.md)] updated CFDI feature to align with the new regulations.  

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

Before you can use [!INCLUDE[prod_short](../../includes/prod_short.md)] for electronic invoicing, you must obtain the appropriate certification, digital stamp, and control numbers from the tax authorities. You must install the certificate on the computer where you generate the CFDI files. Learn more in [Set up electronic invoicing](how-to-set-up-electronic-invoicing.md). Refer to [Servicio de Administracíon Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website, for information about SAT certificates and keys.  

You can use different SAT certificates for company branches. In addition to the SAT certificate you specify on the **General Ledger Setup** page, you can assign a separate SAT certificate for each location associated with a company branch. To use this feature, you must enable the **Multiple SAT Certificates** option on the **General Ledger Setup** page:

- If the option isn't enabled, the certificate from the **General Ledger Setup** page is used to sign all electronic documents.
- If the option is enabled, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks the **SAT Certificate** field on the **Location Card** and uses it for documents associated with that location.
- For transfer shipments, the certificate is determined by the **Transfer-From Code** location.
- The **SAT Certificate Name** and **SAT Certificate Source** fields on the posted document card show the SAT certificate used to sign the electronic document.

> [!TIP]
> Use the **Set up Mexican CFDI information** assisted setup guide to map information about your company and how you use [!INCLUDE [prod_short](../../includes/prod_short.md)] to the various fields in the CFDI files.

You must also specify the web services that you use to communicate with the PAC to obtain digital stamps. Learn more in [Set up PAC Web Services](how-to-set-up-pac-web-services.md).

> [!IMPORTANT]  
> SAT certified more than one PAC in Mexico, and you must obtain the appropriate information to communicate with the PAC of your choice.  

You must also specify information about your company and each of your customers and vendors. Learn more in [Set up electronic invoicing](how-to-set-up-electronic-invoicing.md).  

## Send electronic documents

When you post an invoice or credit memo, you can send it to your customer. But first you must obtain a digital stamp from the PAC. [!INCLUDE[prod_short](../../includes/prod_short.md)] communicates with the PAC through web services to request a stamp, and your company and the PAC digitally sign the document automatically.  

When you send an electronic invoice or credit memo to your customer, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses the email address that you specified on the **Company Information** page. The document is sent to the email address that you specified on the **Customer Card** page for the bill-to customer on the invoice or credit memo. On the **General Ledger Setup** page, you can also choose to include the documents as PDF files in the email that is sent.  

> [!IMPORTANT]  
> The users who send electronic invoices must be able to send mail using the Simple Mail Transfer Protocol (SMTP). Depending on the configuration in your company, you might have to grant explicit permissions to each relevant user and computer.  

If you also want to print the documents, the documents include a Quick Response (QR) bar code and other information that identifies the related electronic invoice. This information makes the printed document computer-readable and provides a link between the electronic document and the printed document. To learn about generating electronic invoices, refer to [Generate Electronic Invoices](how-to-generate-electronic-invoices.md).  

## Cancel documents

You might have to revert a transaction, such as if you have to change the location of a shipment for some reason. You might also have to send such cancellations as electronic documents.  

When you send a cancellation, you must specify a reason for the cancellation, and which document substitutes the canceled document.  

The following table provides an overview of the options for the **CFDI Cancellation Reason** field as of February 2022:

|Option   |Description  |
|---------|-------------|
|01     |Voucher issued with errors in relation.|
|02     |Voucher issued with unrelated errors.|
|03     |The operation wasn't carried out.|
|04     |Related nominative operation in a global invoice.|

If you choose code *01*, then you must also specify the document that substitutes the canceled document in the **Substitution Document No.** field.  

### Send a posted sales invoice for cancellation

1. Open the posted sales invoice that you want to cancel, and then select **Cancel**.  
1. Select **Cancel Request** and confirm. This action allows you to send the cancellation request to the PAC service and receive a cancellation ID for the document.  
1. After you receive a successful response from PAC service, the status is updated to **Cancel In Progress**. The cancellation ID is then taken from the response and updated in the document. This step updates the **Date/Time Stamped** field.  
1. If the error message appears, the status is updated to **Cancel Error**. The error details are shown in the **Error Code** and **Error Description** fields. This step updates the **Date/Time Stamped** field.  

### Send a request to update the status

The SAT authorities need to process and approve the document that you need to cancel. The information about the status should be requested from the PAC service.  

Use the **Get Response** to check and update the cancellation status from the SAT authorities.

> [!NOTE]  
> The possible responses **EnProceso**, **Rechazado**, and **Cancelado** update the **Electronic Document Status** field for the next values respectively: **Cancel In Progress**, **Cancel Error**, or **Canceled**.

### Manually cancel a posted sales invoice

In some cases, when the system can't process the document properly due to incorrect reason codes or classification issues by SAT, you can manually force cancellation. Just select the **Mark as Canceled** action in the menu to cancel a posted sales invoice manually.

### E-Invoice status request batch

The user can schedule a batch job to process a document with **Electronic Document Status** equals **Cancel Error**, and **Cancel In Progress**.  

## Communication component

Technically, the [!INCLUDE[prod_short](../../includes/prod_short.md)] component for electronic invoicing deploys in a library assembly, Microsoft.Dynamics.NAV.MX.dll, which is included automatically with [!INCLUDE[prod_short](../../includes/prod_short.md)]. The component handles the communication with the PAC web services and also generates the QR codes that are included in the printed documents.  

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
