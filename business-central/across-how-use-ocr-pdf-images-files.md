---
title: Use OCR to turn PDF into e-invoices
description: Describes how you can use an OCR service to convert incoming PDF or image files to electronic documents.
documentationcenter: ''
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 05/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Use OCR to turn PDF and image files into electronic documents

From PDF or image files that you receive from your trading partners, you can have an external OCR service (Optical Character Recognition) generate electronic documents that can be converted to document records in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, when you receive an invoice in PDF format from your vendor, you can [send it to the OCR service from the Incoming Documents page](#to-send-a-pdf-or-image-file-to-the-ocr-service-from-the-incoming-documents-page).

As an alternative to sending the file from the **Incoming Documents** page, the OCR service can offer the option to [process files forwarded to a dedicated email address](#to-send-a-pdf-or-image-file-to-the-ocr-service-by-email). Then, when you receive the electronic document back, a related incoming document record is created automatically in [!INCLUDE[prod_short](includes/prod_short.md)].

After some seconds, the OCR service sends the processed file to the **Incoming Documents** page as an electronic document record that can be [converted to a purchase invoice for the vendor](#to-receive-the-resulting-electronic-document-from-the-ocr-service), a sales invoice, credit memo, or a journal entry.

Because OCR is based on optical recognition, it's likely that the OCR service interprets characters in your PDF or image files wrongly when it first processes a certain vendor's documents, for example. It might not interpret the company logo as the vendor's name or it might misinterpret the total amount on a receipt because of its layout. To avoid these errors going forward, you can correct the errors in a separate version of the **Incoming Document** page. Then you send the corrections back to the OCR service to train it to interpret the specific characters and fields correctly next time it processes a PDF or image document for the same vendor. To learn more, go to [Train the OCR service to avoid errors](across-how-use-ocr-pdf-images-files.md#to-train-the-ocr-service-to-avoid-errors).

A dedicated job queue entry processes the traffic of files to and from the OCR service. This job queue is created automatically when you enable the external OCR service connection. To learn more, go to [Set Up Incoming Documents](across-how-setup-income-documents.md).

> [!NOTE]
> The OCR feature is provided by external providers. Choose a service package that is appropriate for your organization and/or country/region. Find services compatible with [!INCLUDE[prod_short](includes/prod_short.md)] and details on available features at [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).

## To send a PDF or image file to the OCR service from the Incoming Documents page

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Create a new incoming document record and attach the file. For more information, see [Create Incoming Document Records](across-how-create-income-document-records.md).  
3. On the **Incoming Documents** page, select one or more lines, and then choose the **Send to Job Queue** action.

   The value in the **OCR Status** field changes to **Ready**. The attached PDF or image file is sent to the OCR service by the job queue according to the schedule, if no errors exist.
4. Alternatively, on the **Incoming Documents** page, select one or more lines, and then choose the **Send to OCR Service** action to immediately send the files for processing.

   The value in the **OCR Status** field changes to **Sent**, if no errors exist.

## To send a PDF or image file to the OCR service by email

From your email application, you can forward an email to the OCR service provider with the PDF or image file attached. For information about the email address to send to, see the OCR service provider's web site.

Since no incoming document record exists for the file, a new record is created automatically on the **Incoming Documents** page when the OCR service sends the resulting electronic document. To learn more, go to [Create Incoming Document Records](across-how-create-income-document-records.md).

> [!NOTE]  
> If you work on a tablet or phone, you can send the file to the OCR service as soon as you take a photo of the document, or you can create an incoming document directly. To learn more, go to [Create an incoming document record by taking a photo](across-how-create-income-document-records.md#create-an-incoming-document-record-by-taking-a-photo).

## To receive the resulting electronic document from the OCR service

The electronic document that is created by the OCR service from the PDF or image file is automatically received into the **Incoming Documents** page by the job queue entry that is set up when you enable the OCR service.

If you aren't using a job queue, or you want to receive a finished OCR document sooner than per the job queue schedule, you can choose the **Receive from OCR Service** action. This option gets any documents that the OCR service completed.

> [!NOTE]  
> If the OCR service is set up to require manual verification of processed documents, the **OCR Status** field contains **Awaiting Verification**. In that case, do the following steps to sign in to the OCR service website to manually verify an OCR document.

1. In the **OCR Status** field, choose the **Awaiting Verification** hyperlink.
2. On the OCR service website, sign in using the credentials of your OCR service account. To learn more, go to [Set up an OCR service](across-how-setup-income-documents.md#to-set-up-an-ocr-service).

   Information for the OCR document displays, showing both the source content of the PDF or image file and the resulting OCR field values.
3. Review the field values and manually edit or enter values in fields that the OCR service tagged as uncertain.
4. Choose the **OK** button. The OCR process is completed and the resulting electronic document is sent to the **Incoming Documents** page in [!INCLUDE[prod_short](includes/prod_short.md)], according to the job queue schedule.
5. Repeat steps 2 through 4 for any other OCR document to be verified.

Now you can proceed to create document records for the received electronic documents in [!INCLUDE[prod_short](includes/prod_short.md)], manually or automatically. For more information, go to the next procedure. You can also [connect the new incoming document record to existing posted or nonposted documents](across-how-connect-disconnect-income-document-records.md) so that the source file is easy to access from [!INCLUDE[prod_short](includes/prod_short.md)].

## To create a purchase invoice from an electronic document received from the OCR service

The following procedure describes how to create a purchase invoice record from a vendor invoice received as an electronic document from the OCR service. The procedure is the same when you create, for example, a general journal line from an expense receipt or a sales return order from a customer.

> [!NOTE]  
> The **Description** and **No.** fields on the created document lines are filled in only if you mapped text found on the OCR document to the two fields in [!INCLUDE[prod_short](includes/prod_short.md)]. You can do this mapping as item references for document lines of the type Item. To learn more, go to [Use Item References](inventory-how-use-item-cross-refs.md). You can also use the **Text-to-Account Mapping** function. To learn more, go to [Map text on an incoming document to a specific vendor, G/L, or bank account](across-how-use-ocr-pdf-images-files.md#to-map-text-on-an-incoming-document-to-a-specific-vendor-account).

1. Select the line for the incoming document, and then choose the **Create Document** action.

A purchase invoice is created in [!INCLUDE[prod_short](includes/prod_short.md)] based on the information in the electronic vendor document that you received from the OCR service. Information is added in the new purchase invoice based on the mapping that you defined as a reference or as text-to-account mapping.

Any validation errors, typically related to wrong or missing data in [!INCLUDE[prod_short](includes/prod_short.md)], show on the **Errors and Warnings** FastTab. To learn more, go to [Handle errors when receiving electronic documents](across-how-use-ocr-pdf-images-files.md#to-handle-errors-when-receiving-electronic-documents).

### To map text on an incoming document to a specific vendor account

For incoming documents, you typically use the **Map Text to Account** action to define that a certain text on a vendor invoice received from the OCR service is mapped to a certain vendor account. Going forward, any part of the incoming document description that exists as a mapping text means that the **Vendor No.** field on resulting document or journal lines of type *G/L Account* are filled with the vendor in question.

In addition to mapping to a vendor account or G/L accounts, you can also map text to a bank account. This option is useful, for example, for electronic documents for expenses that are already paid, and for which you want to create a general journal line that is ready to post to a bank account.

1. Select the relevant incoming document line, and then choose the **Map Text to Account** action. The **Text-to-Account Mapping** page opens.
2. In the **Mapping Text** field, enter any text that occurs on vendor invoices that you want to create purchase documents or journal lines for. You can enter up to 50 characters.
3. In the **Vendor No.** field, enter the vendor that the resulting purchase document or journal line is for.
4. In the **Debit Acc. No.** field, enter the debit-type G/L account to add on the resulting purchase document or journal line of type G/L Account.
5. In the **Credit Acc. No.** field, enter the credit-type G/L account to insert on resulting purchase document or journal line of type G/L Account.

   > [!NOTE]
   > Don't use the **Bal. Source Type** and **Bal. Source No.** fields with incoming documents. They're used for automatic payment reconciliation only. To learn more, go to [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).
6. Repeat steps 2 through 5 for all text on incoming documents that you want to automatically create documents for.

## To handle errors when receiving electronic documents

1. On the **Incoming Documents** page, select the line for an electronic document received from the OCR service with errors, indicated by the *Error* value in the **OCR Status** field.
2. Choose the **Edit** action to open the **Incoming Document** page.
3. On the **Errors and Warnings** FastTab, select the message, and then choose the **Open Related Record** action.
4. The page that contains the wrong or missing data, such as a vendor card with a missing field value, opens.
5. Correct the error or errors as described in each error message.
6. Proceed to process the incoming electronic document by choosing the **Create Manually** action again.
7. Repeat steps 5 and 6 for any remaining errors until the electronic document can be received successfully.

## To train the OCR service to avoid errors

Because OCR is based on optical recognition, the OCR service can wrongly interpret characters in your PDF or image files when it first processes documents from a certain vendor, for example. It might not interpret the company logo as the vendor's name or it might misinterpret the total amount on an expense receipt because of its layout. To avoid such errors going forward, you can correct data received by the OCR service and then send the feedback to the service.

The **OCR Data Correction** page, which you open from the **Incoming Document** page, shows the fields from the **Financial Information** FastTab in two columns, one with the OCR data editable and one with the OCR data read-only. When you choose the **Send OCR Feedback** button, the content of the **OCR Data Correction** page is sent to the OCR service. Next time the service processes PDF or image files that contain the data in question, your corrections will be incorporated to improve the document recognition.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Open an incoming document record that contains data received from the OCR service that you want to correct.
3. On the **Incoming Document** page, choose the **Correct OCR Data** action.
4. On the **OCR Data Correction** page, overwrite the data in the editable column for each field that has an incorrect value.
5. To undo corrections that you made since you opened the **OCR Data Correction** page, choose the **Reset OCR Data** action.
6. To send the corrections to the OCR service, choose the **Send OCR Feedback** action.
7. To save the corrections, close the **OCR Data Correction** page.

The fields on the **Financial Information** FastTab on the **Incoming Document** page update with any new values that you entered in step 4.

## Related information

[Create Incoming Document Records](across-how-create-income-document-records.md)  
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
