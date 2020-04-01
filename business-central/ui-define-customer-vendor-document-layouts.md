---
title: Assign Special Document Layouts to Customers or Vendors| Microsoft Docs
description: When custom report layouts are defined, you can select them from customer and vendor cards to specify that the selected layouts will be used for documents that you crate for the customer or vendor in question.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 04/01/2020
ms.author: sgroespe

---
# Define Document Layouts for Customers and Vendors
When custom report layouts are defined, you can select them from customer and vendor cards to specify which layouts will be used for different types of documents that you crate for the customer or vendor in question. The value in the **Usage** field, defines which process the document layout will be used for, such as **Reminder**, **Shipment**, and **Confirmation**.

In addition to setting up which layouts to use for what document, you can save time when sending documents to different customer or vendor contacts by setting up specific contacts' email addresses to use with specific documents. For example, customer statements will be sent to accountant contacts, sales orders to your customers' purchasers, and purchase orders to vendors' salespeople or account managers.

When you define a document layout for a customer or vendor, you can also specify the email address of the contact person that must receive the document. You can quickly do this with the **Select Email from Contacts** function, which automatically filters to contact email addresses registered for the customer or vendor in question.

Before you can define which document layout to use for which processes, and which contact to send the document to, you must load all the available reports (documents) from the **Report Selections** page. You can quickly do this with the **Copy from Report Selection** function.

The following describes how to define sales document layouts from a customer card. The steps are the same for purchase document layouts from a vendor card.

## To enable all available sales documents for a customer
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the card of the customer for whom you want to define document layouts per business process.
3. On the **Customer Card** page, choose the **Document Layouts** page.
4. On the **Document Layouts** page, choose the **Copy from Report Selection** action.

The **Document Layouts** page for the customer in question is filled with all the report layouts for sales that exist in the system. For more information about they were created, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

You can now proceed to adjust the list with any custom report layouts or email addresses for the contacts that the documents must be sent to.

## To select a custom report layout to use for the sales document layout
If one or more of the report layouts that are defined in the **Document Layouts** page for the customer do not have a custom report layout defined, then you can quickly do that.

1. On the **Document Layouts** page, on the line for a report layout that you want to use a custom layout for, choose the **Custom Layout Description** field. The field is either filled if customer layout is already selected or blank.
2. On the **Custom Report Layouts** page, select the special document layout that you want to use for the sales document type in question. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

## To set up which contact receives which document layout for a customer
You can save time when sending documents to different customers or vendor contacts by specifying contact email addresses on the different lines on the **Document Layouts** page. For example, customer statements can be sent to accountant contacts, sales orders to your customers' purchasers, and purchase orders to vendors' salespeople or account managers.

1. On the **Document Layouts** page, on the line for a report layout that you want to send to a specific contact for the customer, choose the **Select Email from Contacts** action.
2. On the **Contacts** page, select the line for the relevant contact, and then choose the **OK** button.

The email address of the contact is now inserted on the document layout line so that the sales document in question, for example, reminders, is always sent to that contact at the customer's company.

## See Also  
[Update Custom Report Layouts](ui-update-report-layouts.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Managing Report Layouts](ui-manage-report-layouts.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
