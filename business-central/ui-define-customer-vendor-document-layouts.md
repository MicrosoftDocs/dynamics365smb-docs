---
title: Assign document layouts to customers or vendors
description: Use document layouts to control the appearance and format of documents such as invoices and orders that you send to customers and vendors.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 21, 9650
ms.date: 11/28/2024
ms.service: dynamics-365-business-central
---
# Define document layouts for customers and vendors

Document layouts use report layouts to define the look and feel of documents that you send to customers and vendors. Business Central provides standard layouts, but you can also tailor custom layouts for each of your business partners. Learn more in [Get started creating report layouts](ui-get-started-layouts.md). You select standard and custom document layouts from customer and vendor cards by choosing the **Document Layouts** action. The value in the **Usage** field defines the process for which the document layout is used. For example, for customers, you might use **Reminder**, **Shipment**, and **Confirmation** types of document layouts.

Document layouts can also save you time when you send documents to customer or vendor contacts by email. For each layout that you assign to the customer or contact, you can by specify one or more contact email addresses. For example, you can send an invoice to the customer's purchasing and warehouse contacts. Adding contact email addresses is easy. On the **Document Layouts** page, the **Select Email from Contacts** action let's you choose from a list of the contact email addresses that you registered for the customer or vendor. You can also add email addresses manually. If you enter multiple addresses, separate them with a semi-colon, and don't add spaces between the addresses.

Before you define which document layout to use for which processes, and which contact to send the document to, load all the available reports (documents) from the **Report Selections** page. You can quickly load the documents by using the **Copy from Report Selection** action on the **Document Layouts** page.

The steps in the following sections describe how to define sales document layouts from the **Customer Card** page. For vendors, the steps are the same from the **Vendor Card** page.

## Load the standard document layouts for sales documents for a customer

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then choose the related link.
1. Open the **Customer Card** page for the customer, and then choose the **Document Layouts** action.
1. On the **Document Layouts** page, choose the **Copy from Report Selection** action.

The **Document Layouts** page displays all layouts that are available for sales documents.

## Select a report layout to use for the sales document layout

The following steps assume that layout you want for the type of document is already created. Learn more about creating layouts in [Get started creating report layouts](ui-get-started-layouts.md).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then select the related link.
1. Open the **Customer Card** page for the customer, and then select the **Document Layouts** action.
1. On the **Document Layouts** page, on the line for document layout that you want to use a report layout for, set the **Email Body Layout** and **Email Attachment Layout** fields. You can choose different layouts for each.

   >![!NOTE]
   > If you want to use a legacy custom report layout, set the layout in the **Custom Layout Description** field. By default, the **Custom Layout Description** field is hidden. If the field isn't available, you can personalize the page to add it. To personalize the page, select the :::image type="content" source="media/ui-experience/settings_icon_small.png" alt-text="The Settings icon."::: icon, and then select **Personalize**. Learn more about legacy custom report layouts in [(Legacy) Create and modify custom report layouts](ui-how-create-custom-report-layout.md)

## Specify which contact receives which document layout for a customer

To save time when you send documents to customer and vendor contacts by email, specify their email addresses on document layouts. For example, you can always send customer statements to their accountant contacts and sales orders to their purchasers, or purchase orders to vendor salespeople.

1. On the **Document Layouts** page, on the line for a report layout that you want to send to a specific contact for the customer, select the **Select Email from Contacts** action.
1. On the **Contacts** page, select one or more contacts, and then select **OK**.

## Related information

[Update Custom Report Layouts](ui-update-report-layouts.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Managing Report Layouts](ui-manage-report-layouts.md)  
[Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
