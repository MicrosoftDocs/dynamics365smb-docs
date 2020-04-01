---
title: Use OCR to Turn PDF into E-Invoices| Microsoft Docs
description: Describes how you can use an OCR service to convert incoming PDF or image files to electronic documents.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 04/01/2020
ms.author: sgroespe

---
# Use OCR to Turn PDF and Image Files into Electronic Documents
From PDF or image files that you receive from your trading partners, you can have an external OCR service (Optical Character Recognition) generate electronic documents that can be converted to document records in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, when you receive an invoice in PDF format from your vendor, you can send it to the OCR service from the **Incoming Documents** page. This is described in the first procedure.

As an alternative to sending the file from the **Incoming Documents** page, you can send the file to the OCR service by email. Then, when you receive the electronic document back, a related incoming document record is created automatically. This is described in the second procedure.

After some seconds, you receive the file back from the OCR service as an electronic invoice that can be converted to a purchase invoice for the vendor. This is described in the third procedure.

Because OCR is based on optical recognition, it is likely that the OCR service will interpret characters in your PDF or image files wrongly when it first processes a certain vendor’s documents, for example. It may not interpret the company logo as the vendor’s name or it may misinterpret the total amount on a receipt because of its layout. To avoid these errors going forward, you can correct the errors in a separate version of the **Incoming Document** page. Then you send the corrections back to the OCR service to train it to interpret the specific characters correctly next time it processes a PDF or image document for the same vendor. For more information, see [To train the OCR service to avoid errors](across-how-use-ocr-pdf-images-files.md#to-train-the-ocr-service-to-avoid-errors).

The traffic of files to and from the OCR service is processed by a dedicated job queue entry, which are created automatically when you enable the related service connection. For more information, see [Set Up Incoming Documents](across-how-setup-income-documents.md).

## To send a PDF or image file to the OCR service from the **Incoming Documents** page
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Create a new incoming document record and attach the file. For more information, see [Create Incoming Document Records](across-how-create-income-document-records.md).  
3. On the **Incoming Documents** page, select one or more lines, and then choose the **Send to Job Queue** action.

    The value in the **OCR Status** field changes to **Ready**. The attached PDF or image file is sent to the OCR service by the job queue according to the schedule, provided that no errors exist.
4. Alternatively, on the **Incoming Documents** page, select one or more lines, and then choose the **Send to OCR Service** action.

The value in the **OCR Status** field changes to **Sent**, provided that no errors exist.

## To send a PDF or image file to the OCR service by email
From your email application, you can send an email to the OCR service provider with the PDF or image file attached. For information about the email address to send to, see the OCR service provider’s web site.

Because no incoming document record exists for the file, a new record will be created automatically on the **Incoming Documents** page when you receive the resulting electronic document from the OCR service. For more information, see [Create Incoming Document Records](across-how-create-income-document-records.md).

> [!NOTE]  
>   If you work on a tablet or phone, you can send the file to the OCR service as soon as you have taken a photo of the document, or you can create an incoming document directly. For more information, see [To create an incoming document record by taking a photo](across-how-create-income-document-records.md#to-create-an-incoming-document-record-by-taking-a-photo).

## To receive the resulting electronic document from the OCR service.
The electronic document that is created by the OCR service from the PDF or image file is automatically received into the **Incoming Documents** page by the job queue entry that is set up when you enable the OCR service.

If you are not using a job queue, or you want to receive a finished OCR document sooner than per the job queue schedule, you can choose the **Receive from OCR Service** button. This will get any documents that are completed by the OCR service.

> [!NOTE]  
>   If the OCR service is set up to require manual verification of processed documents, then the **OCR Status** field will contain **Awaiting Verification**. In that case, perform the following steps to log in to the OCR service website to manually verify an OCR document.

1. In the **OCR Status** field, choose the **Awaiting Verification** hyperlink.
2. On the OCR service website, log in using the credentials of your OCR service account. These are the credentials you also used when setting up the service. For more information, see [To set up an OCR service](across-how-setup-income-documents.md#to-set-up-an-ocr-service).

    Information for the OCR document is displayed, showing both the source content of the PDF or image file and the resulting OCR field values.
3. Review the various field values and manually edit or enter values in fields that the OCR service has tagged as uncertain.
4. Choose the **OK** button. The OCR process is completed and the resulting electronic document is sent to the **Incoming Documents** page in [!INCLUDE[d365fin](includes/d365fin_md.md)],  according to the job queue schedule.
5. Repeat step 4 for any other OCR document to be verified.

Now you can proceed to create document records for the received electronic documents in [!INCLUDE[d365fin](includes/d365fin_md.md)], manually or automatically. For more information, see the next procedure. You can also connect the new incoming document record to existing posted or non-posted document so that the source file is easy to access from [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Process Incoming Documents](across-process-income-documents.md).

## To create a purchase invoice from an electronic document received from the OCR service
The following procedure describes how to create a purchase invoice record from a vendor invoice received as an electronic document from the OCR service. The procedure is the same when you create, for example, a general journal line from an expense receipt or a sales return order from a customer.

> [!NOTE]  
>   The **Description** and **No.** fields on the created document lines will only be filled if you have first mapped text found on the OCR document to the two fields in [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can do this mapping as item cross-references, for document lines of type Item. For more information, see [Use Item Cross References](inventory-how-use-item-cross-refs.md). You can also use the Text-to-Account Mapping function. For more information, see [To map text on an incoming document to a specific vendor, G/L, or bank account](across-how-use-ocr-pdf-images-files.md#to-map-text-on-an-incoming-document-to-a-specific-vendor-account).

1. Select the line for the incoming document, and then choose the **Create Document** action.

A purchase invoice will be created in [!INCLUDE[d365fin](includes/d365fin_md.md)] based on the information in the electronic vendor document that you received from the OCR service. Information will be inserted in the new purchase invoice based on the mapping that you have defined as a cross-reference or as text-to-account mapping.

Any validation errors, typically related to wrong or missing master data in [!INCLUDE[d365fin](includes/d365fin_md.md)], will be shown on the **Errors and Warnings** FastTab. For more information, see [To handle errors when receiving electronic documents](across-how-use-ocr-pdf-images-files.md#to-handle-errors-when-receiving-electronic-documents).

### To map text on an incoming document to a specific vendor account
For incoming documents, you typically use the **Map Text to Account** action to define that a certain text on a vendor invoice received from the OCR service is mapped to a certain vendor account. Going forward, any part of the incoming document description that exists as a mapping text means that the **No.** field on resulting document or journal lines of type G/L Account are filled with the vendor in question.

In addition to mapping to a vendor account or G/L accounts, you can also map to a bank account. This is practical, for example, for electronic documents for expenses that are already paid where you want to create a general journal line that is ready to post to a bank account.

1. Select the relevant incoming document line, and then choose the **Map Text to Account** action. The **Text-to-Account Mapping** page opens.
3. In the **Mapping Text** field, enter any text that occurs on vendor invoices that you want to create purchase documents or journal lines for. You can enter up to 50 characters.
4. In the **Vendor No.** field, enter the vendor that the resulting purchase document or journal line will be created for.
5. In the **Debit Acc. No.** field, enter the debit-type G/L account that will be inserted on resulting purchase document or journal line of type G/L Account.
6. In the **Credit Acc. No.** field, enter the credit-type G/L account that will be inserted on resulting purchase document or journal line of type G/L Account.

    > [!NOTE]
    > Do not use the **Bal. Source Type** and **Bal. Source No.** fields in connection with incoming documents. They are used for automatic payment reconciliation only. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

7. Repeat steps 2 through 5 for all text on incoming documents that you want to automatically create documents for.

## To handle errors when receiving electronic documents
1. On the **Incoming Documents** page, select the line for an electronic document received from the OCR service with errors. This is indicated by the Error value in the **OCR Status** field.
2. Choose the **Edit** action to open the **Incoming Document** page.
3. On the **Errors and Warnings** FastTab, select the message, and then choose the **Open Related Record** action.
4. The page that contains the wrong or missing data, such as a vendor card with a missing field value, opens.
5. Correct the error or errors as described in each error message.
6. Proceed to process the incoming electronic document by choosing the **Create Manually** action again.
7. Repeat steps 5 and 6 for any remaining errors until the electronic document can be received successfully.

## To train the OCR service to avoid errors
Because OCR is based on optical recognition, it is likely that the OCR service will interpret characters in your PDF or image files wrongly when it first processes documents from a certain vendor, for example. It may not interpret the company logo as the vendor’s name or it may misinterpret the total amount on an expense receipt because of its layout. To avoid such errors going forward, you can correct data received by the OCR service and then send the feedback to the service.

The **OCR Data Correction** page, which you open from the **Incoming Document** page, shows the fields from the **Financial Information** FastTab in two columns, one with the OCR data editable and one with the OCR data read-only. When you choose the **Send OCR Feedback** button, the content of the **OCR Data Correction** page is sent to the OCR service. Next time the service processes PDF or image files that contain the data in question, your corrections will be incorporated to avoid the same errors.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Open an incoming document record that contains data received from OCR service, which you want to correct.
3. On the **Incoming Document** page, choose the **Correct OCR Data** action.
4. On the **OCR Data Correction** page, overwrite the data in the editable column for each field that has an incorrect value.
5. To undo corrections that you have made since you opened the **OCR Data Correction** page, choose the **Reset OCR Data** action.
6. To send the corrections to the OCR service, choose the **Send OCR Feedback** action.
7. To save the corrections, close the **OCR Data Correction** page.

The fields on the **Financial Information** FastTab on the **Incoming Document** page are updated with any new values that you entered in step 4.

## See Also
[Process Incoming Documents](across-process-income-documents.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
