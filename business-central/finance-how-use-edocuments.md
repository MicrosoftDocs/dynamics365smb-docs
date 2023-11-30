---
title: Use e-documents in sales and purchases
description: Learn how to use e-documents functionality that is related to sales and purchase invoices.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, sales, purchase
ms.search.form: 42, 43, 51, 6103, 6133, 6121, 9301, 9305, 9308
ms.date: 10/03/2023
ms.author: altotovi
---

# Use e-documents in sales and purchases

You can use configured electronic documents (e-documents) with sales and purchase documents.

You can use the following documents with e-documents functionality:  

- Sales: 
    - Sales invoices
    - Sales orders
    - Sales credit memos
    - Service invoices
    - Service credit memos
    - Finance charge memos
    - Reminders
- Purchase: 
    - Purchase invoices
    - Purchase orders (only create new document)
    - Purchase credit memos
    - General journals

> [!NOTE]
> Currently, a purchase order can be used only when you create the document from the e-document from your vendor. However, you can't update the existing document with lines that you got from your vendor.  

## E-documents in sales

To create and send an e-invoice to a customer, you must create and post the sales invoice. To learn more about the standard process, see [Invoice Sales](sales-how-invoice-sales.md).

After you post the sales document, open the **Posted Sales Invoice** page to access the related **E-Document** page.

### View e-documents

To view existing e-documents, follow these steps.

1. On the **Posted Sales Invoice** page, select **E-Document** \> **Open E-Document**.
2. On the **E-Document** page, on the header, you can view basic information about the posted invoice.
3. The **Record** field shows the document number of the posted sales invoice. Select the link to open the document.
4. In the **Electronic Document Status** field, you can view the real-time status of the document and its location in the process pipeline. If the document is posted, the status is **Processed**.

### E-document statuses and logs

For details about the service status level of your e-document, check the **E-Document Service Status** FastTab. On the lines, the system shows one or more services that the document used. In the most common scenario, each document uses only one service. However, a document can use multiple services.

- Check the **E-Document Service Code** field to determine which service was used.
- Check the **E-Document Status** field to determine the current service status for this document.
- If you want more details, select the **Logs** field for the service on the **E-Document Logs** page. A chronological overview of the different statuses for the document is shown.
- Check the **Entry No.** and **Created At** fields, and other information on the **E-Document Logs** page. In the **E-Document Status** field, the first status is **Exported**, which indicates that the e-document file has been created. The next status is **Sent**, which indicates that document was sent to the service provider, if configured.

For more insights, select the entry that has the **Exported** status, and then run one of the following actions:

- **Open Mapping Logs** – Get an overview of all exported fields from the sourced tables in the **Original Value** field. If you used transformation rules in the export process, you can also get the final value in the **New Value** field.
- **Export File** – Export the XML file for manual review.

To view the communication between yourself and the service that you're sending your document to, use the **Communication Logs** field. Open the **E-Document Communication Logs** page to view details about the request and reasons message with that service.

If there's an issue with the service provider, and the document can't be sent, look for the following indicators on the **E-Document** page:

- The **Electronic Document Status** field on the header shows the **Error** status.
- The **E-Document Status** field on the **E-Document Service Status** FastTab shows the **Sending Error** status.
- The **Error and Warnings** FastTab contains one or more messages that provide the cause of the issue.

After the issue is fixed, manually run the **Send Document** actions. If you need different actions, such as **Recreated Document**, **Cancel Document**, or **Get Approval**, you can run them.

## E-documents in purchases

The receipt of purchase electronic invoices in Dynamics 365 Business Central can be done as a batch job or manually.

### Run the batch job

> [!NOTE]
> This batch job is for automated collection of your incoming invoices. It can work only in a country or region where the functionality exists.

Every time that a job queue is run, if the external service has incoming invoices that were sent from your vendor, the system collects and imports those invoices. To complete the process, follow these steps.

1. After the batch job has been finished running, the newly imported invoices are listed on the **E-Documents** page, together with their basic detail information.
2. To view more details, open a specific e-document.
3. If there were no errors or issues in the e-document and its mapping, the **Record** field shows the document number of the purchase invoice that the system automatically created. Select the link to open the document. This system-created document isn't the posted document.
4. To go directly to the purchase document, select the **Record** field. After you open the **Purchase Invoice** page, check the document. Then, if everything is correct, post the document.
5. When you post the purchase document, the **Record** field on the **E-Document** is updated from **Invoice** to **Purchase Invoice**, and the number of the posted purchase document is available. You can select the number to open the posted purchase invoice.

Details about logs are the same as they are in the sales process for e-documents.

Because errors in the sales process are mostly related to the availability of the service, the incoming document can contain multiple reasons. The most common reason for an error is that system can't recognize the lines on the e-document that you got from your vendor. Therefore, it can't enter lines in your purchase invoice.

There are two common errors:

- If you want to use this specific line from your vendor invoice that was directly posted to the general ledger (G/L) account, you must have correctly configured the **Mapping Text** value. To bypass this error if you want to use G/L accounts, select **Map Text to Account** to create a specific mapping of the **Mapping Text** value with the **Debit Acc. No.** value that you want to use.
- If you want to track the inventory and use lines from your vendor invoice to fill in items on your document lines, you must have correctly configured the **Item Reference No.** value. To bypass this error, map the external item with your item numbers by using the item reference list. To learn more, see [Use Item References](inventory-how-use-item-cross-refs.md).

After you fix the errors and warnings, you can manually specify when the system should create a purchase invoice based on your setup by selecting **Create Document**.

### Manually import invoices

To manually import external e-documents, follow these steps.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Service**, and then select the related link.
2. On the **E-Document Service** page, select the active service. 
3. Select **Receive**, and upload the e-document file that you got from the vendor.
4. If an error message occurs, open the e-document to fix the issues.
5. When you've finished fixing issues, in the **Import Manually** group, select **Create Document**.
6. After the document is created in Business Central, you can view it just as you do if you use a batch job.

## Overview of e-document statuses

To get a better overview of all e-documents in the company, you can select the **Accountant** role center where e-document statuses exist. There, you can find e-document activities that have the following statuses:

- **Outgoing e-documents:**

    - Processed
    - In Progress
    - Error

- **Incoming e-documents:**

    - Processed
    - In Progress
    - Error

## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
