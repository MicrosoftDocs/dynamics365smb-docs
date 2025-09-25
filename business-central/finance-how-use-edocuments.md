---
title: Use e-documents in sales
description: Learn how to use e-documents functionality that is related to sales.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, sales, deliver
ms.search.form: 42, 43, 132, 6103, 6133, 6121, 9301, 9305
ms.date: 09/25/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Use e-documents in the sales process

You can use configured electronic documents (e-documents) with the following sales documents:  

- Sales invoices
- Sales orders
- Sales credit memos
- Service invoices
- Service credit memos
- Finance charge memos
- Reminders

## E-documents in sales  

To create and send an e-invoice to a customer, you must create and post the sales invoice. To learn more about the standard process, go to [Invoice Sales](sales-how-invoice-sales.md).

Before posting, you can choose to add the attachment to the invoice if you want to embed it in the Peppol file format.

After you post the sales document, open the **Posted Sales Invoices** page to access the related **E-Documents** page.

### View e-documents

To view existing e-documents, follow these steps.

1. On the **Posted Sales Invoices** page, select **E-Document**, and then select **Open E-Document**.
2. On the **E-Documents** page, on the header, you can view basic information about the posted invoice.
3. The **Record** field shows the document number of the posted sales invoice. Select the link to open the document.
4. In the **Electronic Document Status** field, you can view the real-time status of the document and its location in the process. If the document is posted, the status is **Processed**.

### Send e-documents via a service and email simultaneously

[!INCLUDE [prod_short](includes/prod_short.md)] offers flexible ways to share documents and information quickly and easily. Document sending profiles let you specify your preferred way to send documents when you post them. For example, you might want to send a document by email or as an electronic document through a service you use. Or, you might want to do both at the same time. To learn more about document sending profiles, go to [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

If you choose the **Post** action from the **Sales Order**, **Sales Invoice** or **Sales Credit Memo** pages, [!INCLUDE [prod_short](includes/prod_short.md)] posts the document as usual. However, if you set up e-document workflow for the customer, it can also start a workflow to create an e-document. Then, when you choose **Post and Send**, [!INCLUDE [prod_short](includes/prod_short.md)] also sends the e-document via email as an attachment.

Depending on whether you enable **Service Integration** on the **E-Document Service** page, you can choose one of the following ways to send documents in the sales process:

- When **Service Integration** is enabled, use the **Post** action to send the e-document to the configured access point.
- When **Service Integration** is enabled, use the **Post and Send** action to send the e-document to the configured access point and as an attachment in an email.
- When **Service Integration** isn't enabled, use the **Post** action to create an e-document that you can download.
- When **Service Integration** isn't enabled, use the **Post and Send** action to send the e-document by email.

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

If there's an issue with the service provider, and the document can't be sent, look for the following indicators on the **E-Documents** page:

- The **Electronic Document Status** field on the header shows the **Error** status.
- The **E-Document Status** field on the **E-Document Service Status** FastTab shows the **Sending Error** status.
- The **Error and Warnings** FastTab contains one or more messages that provide the cause of the issue.

After the issue is fixed, manually run the **Send Document** actions. If you need different actions, such as **Recreated Document**, **Cancel Document**, or **Get Approval**, you can run them.

## Manually create e-documents when they weren't created automatically

Using e-documents requires some configuration, and sometimes people get that wrong. If there was a problem with your setup when you posted sales documents, [!INCLUDE [prod_short](includes/prod_short.md)] might not automatically create e-documents for them. If that happens, after you fix your setup, you can generate new e-documents from the posted documents.

To check whether [!INCLUDE [prod_short](includes/prod_short.md)] created an e-document, open the **Posted Sales Invoice** page and select the **Open E-Document** action. If [!INCLUDE [prod_short](includes/prod_short.md)] doesn't find a related e-document, a message displays. Review your settings for your e-documents and correct any mistakes. To learn more about the setup, go to [Set up e-documents](finance-how-setup-edocuments.md).

When you're ready, you can run the **Create New E-Document** action to generate an e-document based on the workflow rules.

## Overview of e-document statuses

To get a better overview of all e-documents in the company, you can select the **Accountant** role center where e-document statuses exist. There, you can find e-document activities that have the following statuses:

- **Outgoing e-documents:**

    - Processed
    - In Progress
    - Error

## Related information

[How to set up e-documents in [!INCLUDE[prod_short](includes/prod_short.md)]](finance-how-setup-edocuments.md)  
[How to use e-documents in purchase](finance-how-use-edocuments-purchase.md)  
[How to extend e-documents in [!INCLUDE[prod_short](includes/prod_short.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
