---
title: Work with incoming documents
description: You can manage incoming external business documents, such as payment receipts or PDFs, manage OCR tasks, and convert files to electronic documents and records.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 03/12/2025
ms.service: dynamics-365-business-central

---
# Incoming documents

External business documents can come into your company as an email attachment or a paper copy that you scan to file. This scenario is typical of purchases, where such incoming document files represent payment receipts for expenses or small purchases.

On the **Incoming Documents** page, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries.

## Usage scenario

You can register files or paper copies received from your trading partners in [!INCLUDE[prod_short](includes/prod_short.md)] and create a document record. For example, a purchase or sales invoice, credit memo or a journal line.

Upload the received files, or use your device's camera to take a photo, and create entries to represent the external documents. Optionally, with PDF or image files, you can have an external optical character recognition (OCR) service generate electronic documents that can then be converted to records inside [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> The OCR feature is provided by external providers. Choose a service package that is appropriate for your organization and/or country/region. Find services compatible with [!INCLUDE[prod_short](includes/prod_short.md)] and details on available features at [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).

For example, when you receive an invoice in PDF format from your vendor, you can send it to the OCR service from the **Incoming Documents** page. Alternatively, some OCR providers offer the option of processing files forwarded to a dedicated email address, which then automatically creates a related incoming document record. After some seconds, you receive the file back from the OCR service as an electronic invoice that can be converted to a purchase invoice for the vendor.

> [!TIP]
> Create incoming document records in [!INCLUDE[prod_short](includes/prod_short.md)] directly from emails sent by vendors using the Outlook add-in. To learn more, go to [Use Business Central as your Business Inbox in Outlook](work-outlook-addin.md).

## Incoming document features

The incoming document process can consist of the following main activities:

* Record the external documents in [!INCLUDE[prod_short](includes/prod_short.md)] by creating lines on the **Incoming Documents** page in the following ways:
  * Manually, either from a PC or from a mobile device, in one of the following ways:
    * Use the **Create from File** button, upload a file, and then fill the relevant fields on the **Incoming Document** page.
    * Use the **New** button, fill the relevant fields on the **Incoming Document** page and manually attach the related file.
    * From a tablet or phone, use the **Create from Camera** button to create a new incoming document record using the device's built-in camera.

      > [!NOTE]
      > To use a mobile phone, you must install the [!INCLUDE [prod_short](includes/prod_short.md)] mobile app. The app is available on the App Store and on Google Play. To learn more, go to [Getting Business Central on your mobile device](install-mobile-app.md).

  * Automatically, by receiving the document from the OCR service as an electronic document after you've uploaded or emailed the related PDF or image file to an OCR service. The **Financial Information** FastTab is automatically filled on the **Incoming Document** page.
* Use an external OCR service to have PDF or image files turned into electronic documents that can be converted to document records in [!INCLUDE[prod_short](includes/prod_short.md)].
* Create new documents or general journal lines for incoming document records by entering the information as you read it from incoming document files.
* Attach incoming document files to purchase and sales documents of any status, including to the vendor, customer, and general ledger entries that result from posting.
* View incoming document records and their attachments from any purchase and sales document or entry, or find all general ledger entries without incoming document records from the **Chart of Accounts** page.

> [!NOTE]
> Files attached to cards and documents on the **Attachments** tab aren't included on the **Incoming Documents** page. To learn more, go to [Manage Attachments, Links, and Notes on Cards and Documents](ui-how-add-link-to-record.md).

| To | See |
| --- | --- |
| Set up the **Incoming Documents** feature and set up the OCR service. |[Set Up Incoming Documents](across-how-setup-income-documents.md) |
| Create incoming document records manually or automatically by taking a photo of a paper receipt, for example. |[Create Incoming Document Records](across-how-create-income-document-records.md) |
| Use an OCR service to turn PDF and image files into electronic documents that can be converted to purchase invoices in [!INCLUDE[prod_short](includes/prod_short.md)], for example. Train the OCR service to avoid errors next time it processes similar data. |[Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md) |
| Connect or remove incoming document records for any non-posted sales or purchase document and to any customer, vendor, or general ledger entry from the document or entry. |[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md) |
| From the **Chart of Accounts** and **General Ledger Entries** pages, use a search function to find general ledger entries for posted documents that don't have incoming document records and then centrally link to existing records or create new ones with attached document files. |[Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md) |
| Get a better overview by setting incoming document records to *Processed* and remove them from the default view. |[Manage Many Incoming Document Records](across-how-manage-many-income-document-records.md) |

## Related information

[Purchasing](purchasing-manage-purchasing.md)  
[Editing Posted Documents](across-edit-posted-document.md)  
[Exchanging Data Electronically](across-data-exchange.md)  
[Business Central and OneDrive for Business Integration](across-onedrive-overview.md)  
[Use Business Central as your Business Inbox in Outlook](work-outlook-addin.md)  
[Send Documents and Emails](ui-how-send-documents-email.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
