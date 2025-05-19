---
title: Send documents and emails
description: You can define content to insert into the body of an email message, for example, a PayPal link. You can also attach documents to email messages.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: SMTP, mail, Microsoft 365, cover, body, PayPal, layout
ms.search.form: 41,
ms.date: 05/19/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Send documents and emails

You can easily share information and documents, such as sales and purchase orders and invoices, by email directly from [!INCLUDE[prod_short](includes/prod_short.md)], without having to open an email app.  

You can send almost all types of documents as PDF attachments. You can also set up a report layout that includes information from the document in the email text, and text that makes the email more friendly. For example, a standard greeting. To learn more, go to [Managing Report and Document Layouts](ui-manage-report-layouts.md).

When you send invoices, you can make it easier for customers to make payments through a payment service, such as PayPal, by automatically adding information and a link to the service in the email. To learn more, go to [Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md).

To enable emails from within [!INCLUDE[prod_short](includes/prod_short.md)], start the **Set Up Email** assisted setup guide. To learn more, go to [Set Up Email](admin-how-setup-email.md).

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] supports only outbound email communications. You can't also receive replies from within the app.

## To send documents by email

This procedure describes how to attach a posted sales invoice to an email as a PDF file, and with document-specific email text. The steps are the same for other documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.
2. Select the invoice, choose the **Print/Send** action, and then choose **Send by Email**.
3. In the **Email** field, choose **Yes (Prompt for Settings)**. To learn more, go to [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

    If the **Email** field on the **Send Document to** page is set to **Yes (Prompt for Settings)**, the **Send Email** page opens. The page shows the contact person in the **To:** field and the document attached as a PDF file. In the **Body** field, you can either enter text manually or you can have the field filled with a document-specific email body that you set up.

4. Choose the **OK** button.
5. In the **To:** field, enter a valid email address. The default value is the customer email address.
6. In the **Subject** field, enter a descriptive subject text. The default value is the customer name and invoice number.
7. In the **Attachment** field, the generated invoice is attached by default as a PDF file.
8. In the **Body** field, enter a short message to the recipient.

    If a document-specific email text is set up on the **Report Selection - Sales** page, the **Body** field is filled in automatically. To learn more, go to [Set Up Reusable Email Texts and Layouts](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts).
9. Choose the **OK** button to send the email message.

> [!NOTE]  
> If you don't want to specify email settings each time you email a document, you can select the **Yes (Use Default Settings)** option in the **Email** field on the **Send Document to** page. In that case, the **Send Email** page won't open. See Step 4. To learn more, go to [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).  

## To compose and send an email

You can quickly compose emails for contacts, customers, vendors, salespeople/purchasers, and bank accounts directly from the pages for those entities. Just choose **Process**, and then **Send Email** to open the email editor. For bank accounts, the **Send Email** action is under **Actions**.

> [!TIP]
> If you often send email messages that are similar, or want to send a bulk communication, using Word templates with email can speed up the process. For example, to advertise a sales campaign. You can create a template for entities such as customers, vendors, and contacts. Templates can generate the content of an email message for you. Templates can even personalize the content for the recipient based on data in [!INCLUDE[prod_short](includes/prod_short.md)]. To learn more, go to [Use Word Templates for Bulk Communication](ui-mail-merge.md).  

### Attach a document to an email

There are several ways to attach documents to emails.

If you're assigned to an email scenario related to the entity you're sending the email to, an attachment might be automatically added to your message. The attachment is added because a default attachment is assigned to the email scenario. You can delete the attachment if you don't want to send it with your message. To learn more, go to [Assign Email Scenarios to Email Accounts](admin-how-setup-email.md#assign-email-scenarios-to-email-accounts).

To attach a file yourself, in the email editor, use the following actions:

* Choose **Add file** to select a file.
* Choose **Add files from default selection** to manually add the default attachment from the email scenario.
* Choose **Add file from source document** to choose a file attached to the document you're working with. The files are either attached to the document itself, or one or more of its lines.

## Documents marked as printed when they're sent

Some documents in [!INCLUDE[prod_short](includes/prod_short.md)] have a field that specifies how many times the document was printed. The number in that field is also updated if you send the document by email because a PDF file is generated for it. The number is updated even if you don't send the email.

## Sent emails and your email outbox

[!INCLUDE[prod_short](includes/prod_short.md)] stores the emails that you send on the **Sent Items** page. It stores the emails to let you resend them, or forward them to someone else. If you can't find an email in your sent items, look for it on the **Email Outbox** page.

> [!NOTE]
> Depending on the extension that your company uses for email, administrators can access a list of messages that people sent, but not the content of the messages

The **Email Outbox** contains the emails that you saved as drafts and emails that failed to send. For example, if the email address was invalid. For messages that failed to send, you can choose **Show Error** or **Investigate Error** to troubleshoot the problem.  

## Related information

[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Set up Email](admin-how-setup-email.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
