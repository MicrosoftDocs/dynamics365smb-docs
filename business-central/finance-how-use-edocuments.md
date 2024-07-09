---
title: Use e-documents in sales
description: Learn how to use e-documents functionality that is related to sales.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, sales, deliver
ms.search.form: 42, 43, 132, 6103, 6133, 6121, 9301, 9305
ms.date: 04/10/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Use e-documents in the sales process

You can use configured electronic documents (e-documents) with the sales documents.

You can use the following sales documents with e-documents functionality:  

- Sales invoices
- Sales orders
- Sales credit memos
- Service invoices
- Service credit memos
- Finance charge memos
- Reminders

## E-documents in sales  

To create and send an e-invoice to a customer, you must create and post the sales invoice. To learn more about the standard process, see [Invoice Sales](sales-how-invoice-sales.md).

After you post the sales document, open the **Posted Sales Invoices** page to access the related **E-Documents** page.

### View e-documents   

To view existing e-documents, follow these steps.

1. On the **Posted Sales Invoices** page, select **E-Document**, and then select **Open E-Document**.
2. On the **E-Documents** page, on the header, you can view basic information about the posted invoice.
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

If there's an issue with the service provider, and the document can't be sent, look for the following indicators on the **E-Documents** page:

- The **Electronic Document Status** field on the header shows the **Error** status.
- The **E-Document Status** field on the **E-Document Service Status** FastTab shows the **Sending Error** status.
- The **Error and Warnings** FastTab contains one or more messages that provide the cause of the issue.

After the issue is fixed, manually run the **Send Document** actions. If you need different actions, such as **Recreated Document**, **Cancel Document**, or **Get Approval**, you can run them.

## Overview of e-document statuses

To get a better overview of all e-documents in the company, you can select the **Accountant** role center where e-document statuses exist. There, you can find e-document activities that have the following statuses:

- **Outgoing e-documents:**

    - Processed
    - In Progress
    - Error


## See also

[How to set up e-documents in [!INCLUDE[prod_short](includes/prod_short.md)]](finance-how-setup-edocuments.md)    
[How to use e-documents in purchase](finance-how-use-edocuments-purchase.md)  
[How to extend e-documents in [!INCLUDE[prod_short](includes/prod_short.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)    
[Financial Management](finance.md)    
[Invoice Sales](sales-how-invoice-sales.md)    
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
