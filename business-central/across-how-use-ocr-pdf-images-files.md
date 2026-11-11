---
title: Use OCR to Turn PDF and Image Files into Electronic Documents
description: Use an OCR service to convert PDF and image files to incoming documents in Business Central, correct recognized data, and create invoices or journal lines.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 11/10/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Use OCR to turn PDF and image files into electronic documents

From PDF or image files that you receive from your trading partners, you can have an external OCR service (Optical Character Recognition) generate electronic documents that you can convert to document records in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, when you receive an invoice in PDF format from your vendor, you can [send it to the OCR service from the Incoming Documents page](#send-a-pdf-or-image-file-to-the-ocr-service-from-the-incoming-documents-page).

As an alternative to sending the file from the **Incoming Documents** page, the OCR service can offer the option to [process files forwarded to a dedicated email address](#send-a-pdf-or-image-file-to-the-ocr-service-by-email). Then, when you receive the electronic document back, a related incoming document record is created automatically in [!INCLUDE[prod_short](includes/prod_short.md)].

When the OCR service finishes processing, [!INCLUDE[prod_short](includes/prod_short.md)] retrieves the electronic document according to the receiving job queue schedule. You can then [create a purchase invoice](#create-a-purchase-invoice-from-an-electronic-document-received-from-the-ocr-service), credit memo, or journal line. Processing time depends on the OCR provider and the job queue schedule.

Because OCR is based on optical recognition, it's likely that the OCR service interprets characters in your PDF or image files wrongly when it first processes a certain vendor's documents, for example. It might not interpret the company logo as the vendor's name or it might misinterpret the total amount on a receipt because of its layout. To help improve recognition, correct the values on the **OCR Data Correction** page and send feedback to the provider. How the provider uses that feedback depends on the service. Learn more in [Train the OCR service to avoid errors](#train-the-ocr-service-to-avoid-errors).

Separate job queue entries send files to the OCR service and receive the results. These entries are created automatically when you enable the OCR service connection. Learn more in [Set Up Incoming Documents](across-how-setup-income-documents.md).

> [!NOTE]
> The OCR feature is provided by external providers. Choose a service package that's appropriate for your organization and/or country/region. Find services compatible with [!INCLUDE[prod_short](includes/prod_short.md)] and details on available features at [Marketplace.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).

## Send a PDF or image file to the OCR service from the Incoming Documents page

Set up and enable the OCR service first. The incoming document must have a PDF or image attachment and an **OCR Service Doc. Template Code**. If an approval workflow applies, complete the approval process before sending the document.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. Create a new incoming document record and attach the file. Learn more in [Create Incoming Document Records](across-how-create-income-document-records.md).
1. On the **Incoming Documents** page, select one or more lines, and then choose the **Send to Job Queue** action.

   The value in the **OCR Status** field changes to **Ready**. The attached PDF or image file is sent to the OCR service by the job queue according to the schedule, if no errors exist.

Alternatively, on the **Incoming Documents** page, select one or more lines, and then choose **Send to OCR Service** to send the files immediately. The **OCR Status** changes to **Sent** if the upload succeeds.

## Send a PDF or image file to the OCR service by email

From your email application, you can forward an email to the OCR service provider with the PDF or image file attached. Refer to the OCR service provider's web site for information about the email address to send to.

Since no incoming document record exists for the file, a new record is created automatically on the **Incoming Documents** page when the OCR service sends the resulting electronic document. Learn more in [Create Incoming Document Records](across-how-create-income-document-records.md).

> [!NOTE]  
> If you work on a tablet or phone, you can send the file to the OCR service as soon as you take a photo of the document, or you can create an incoming document directly. Learn more in [Create an incoming document record by taking a photo](across-how-create-income-document-records.md#create-an-incoming-document-record-by-taking-a-photo).

## Receive the resulting electronic document from the OCR service

The electronic document that is created by the OCR service from the PDF or image file is automatically received into the **Incoming Documents** page by the job queue entry that is set up when you enable the OCR service.

If you aren't using a job queue, or you want to receive a finished OCR document sooner than per the job queue schedule, you can choose the **Receive from OCR Service** action. This option gets any documents that the OCR service completed.

> [!NOTE]  
> If the OCR service requires manual verification, the **OCR Status** field shows **Awaiting Verification**. Follow your provider's instructions to verify the recognized values.

1. In the **OCR Status** field, choose the **Awaiting Verification** hyperlink.
1. Sign in to the OCR service website and verify the document according to your provider's instructions. Learn more in [Set up an OCR service](across-how-setup-income-documents.md#set-up-an-ocr-service).

After verification and processing are complete, the receiving job queue retrieves the document. You can also choose **Receive from OCR Service** to retrieve available results.

Now you can proceed to create document records for the received electronic documents in [!INCLUDE[prod_short](includes/prod_short.md)], manually or automatically. Learn more in the next procedure. You can also [connect the new incoming document record to existing posted or nonposted documents](across-how-connect-disconnect-income-document-records.md) so that the source file is easy to access from [!INCLUDE[prod_short](includes/prod_short.md)].

## Create a purchase invoice from an electronic document received from the OCR service

The following procedure describes how to create a purchase invoice from a vendor invoice received as an electronic document from the OCR service. To create a general journal line instead, choose **Create Journal Line**.

> [!NOTE]  
> Review how the imported lines identify items or G/L accounts. Use item references to identify items. Learn more in [Use Item References](inventory-how-use-item-cross-refs.md). For G/L account lines, use **Text-to-Account Mapping** or configure the default accounts for non-item lines in **Purchases & Payables Setup**. Learn more in [Map text on an incoming document to accounts](#map-text-on-an-incoming-document-to-accounts).

1. Select the line for the incoming document, and then choose the **Create Document** action.

A purchase invoice is created in [!INCLUDE[prod_short](includes/prod_short.md)] based on the information in the electronic vendor document that you received from the OCR service. Information is added in the new purchase invoice based on the mapping that you defined as a reference or as text-to-account mapping.

Any validation errors, typically related to wrong or missing data in [!INCLUDE[prod_short](includes/prod_short.md)], show on the **Errors and Warnings** FastTab. Learn more in [Handle errors when receiving electronic documents](#handle-errors-when-receiving-electronic-documents).

### Map text on an incoming document to accounts

Use **Map Text to Account** to map text on incoming purchase document lines to debit or credit G/L accounts. The **Vendor No.** field limits a purchase-line mapping to a specific vendor. Leave it blank to make the mapping available across vendors.

For general journal conversion, the mapping text must match the incoming document's **Vendor Name**, without regard to case. If the incoming document has a **Vendor No.**, that vendor is used as the balancing account. Otherwise, the conversion uses **Bal. Source Type** and **Bal. Source No.** from the matching rule, or the balancing account on the journal batch. For example, you can specify **Bank Account** and a bank account number for an expense that's already paid.

1. Select the relevant incoming document line, and then choose the **Map Text to Account** action. The **Text-to-Account Mapping** page opens.
1. In **Mapping Text**, enter text from the incoming purchase document line, or the **Vendor Name** for general journal conversion. You can enter up to 250 characters.
1. For a vendor-specific purchase-line mapping, enter **Vendor No.**.
1. In **Debit Acc. No.**, enter the G/L account to debit, such as the expense account for a purchase invoice.
1. In **Credit Acc. No.**, enter the G/L account to credit, such as the account for a purchase credit memo.
1. If general journal conversion needs a balancing account other than a vendor, fill in **Bal. Source Type** and **Bal. Source No.** as described earlier.
1. Repeat the procedure for each mapping rule.

## Handle errors when receiving electronic documents

Conversion errors appear on the **Errors and Warnings** FastTab. They can occur even when **OCR Status** is **Success**, because recognizing the document and creating a Business Central document are separate steps.

1. On the **Incoming Documents** page, open the incoming document that failed to convert.
1. On the **Errors and Warnings** FastTab, select an error, and then choose **Open Related Record** if it's available.
1. Correct the wrong or missing data identified by the message, such as a missing value on a vendor card.
1. Return to the incoming document and choose **Create Document** to retry conversion, or **Create Journal Line** if you're creating a journal line.
1. Repeat the corrections and retry until the conversion succeeds.

## Train the OCR service to avoid errors

Because OCR is based on optical recognition, the OCR service can wrongly interpret characters in your PDF or image files when it first processes documents from a certain vendor, for example. It might not interpret the company logo as the vendor's name or it might misinterpret the total amount on an expense receipt because of its layout. To help improve recognition, you can correct data received from the OCR service and send feedback to the service.

The **OCR Data Correction** page, which you open from the **Incoming Document** page, shows the fields from the **Financial Information** FastTab in two columns, one with the OCR data editable and one with the OCR data read-only. Choose **Send OCR Feedback** to send your corrections to the OCR service. The effect on future recognition depends on the provider.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. Open an incoming document record that contains data received from the OCR service that you want to correct.
1. On the **Incoming Document** page, choose the **Correct OCR Data** action.
1. On the **OCR Data Correction** page, overwrite the data in the editable column for each field that has an incorrect value.
1. To send the corrections to the OCR service, choose **Send OCR Feedback**. The page closes when the feedback is sent successfully. To keep the corrections without sending feedback, close the page instead.

The fields on the **Financial Information** FastTab on the **Incoming Document** page update with your corrections. To restore the original values received from the OCR service, choose **Reset OCR Data** on the **OCR Data Correction** page.

## Related information

[Create Incoming Document Records](across-how-create-income-document-records.md)  
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
