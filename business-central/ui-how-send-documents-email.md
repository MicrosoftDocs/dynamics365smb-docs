---
title: Set Up Document-Specific Email Content | Microsoft Docs
description: You can define content to insert into the body of an email message, for example, a PayPal link. You can also attach documents to email messages.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.workload: na
ms.search.keywords: SMTP, mail, Microsoft 365, cover, body, PayPal, layout
ms.date: 04/01/2021
ms.author: edupont

---
# Send Documents and Emails
You can easily share information and documents, such as sales and purchase orders and invoices, by email directly from [!INCLUDE[prod_short](includes/prod_short.md)]], without having to open an email app. 

You can send almost all types of documents as PDF attachments. Alternatively, you can set up a report layout that includes information from the document in the email text, along with text that makes the email more friendly, for example, a standard greeting. For more information, see [Managing Report and Document Layouts](ui-manage-report-layouts.md). <!--this topic does not mention how to set up a layout for email. Need to investigate.-->

When you send invoices, you can make it easier for customers to make payments through a payment service, such as PayPal, by automatically adding information and a link to the service in the email. For more information, see [Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md).

To enable emails from within [!INCLUDE[prod_short](includes/prod_short.md)], start the **Set Up Email** assisted setup guide. For more information, see [Set Up Email](admin-how-setup-email.md).

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)]] supports only outbound email communications. You cannot also receive replies from within the app.

## To send documents by email
This procedure describes how attach a posted sales invoice to an email as a PDF file, and with document-specific email text. <!--update this-->

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.
2. Select the invoice, and then choose the **Print/Send** action.
3. In the **Email** field, choose **Yes (Prompt for Settings)**. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).
    
    If the **Email** field on the **Send Document to** page is set to **Yes (Prompt for Settings)**, then the **Send Email** page opens pre-filled with the contact person in the **To:** field and the document attached as a PDF file. In the **Body** field, you can either enter text manually or you can have the field filled with a document-specific email body that you have set up.

4. Choose the **OK** button.
5. In the **To:** field, enter a valid email address. The default value is the customer email address.
6. In the **Subject** field, enter a descriptive subject text. The default value is the customer name and invoice number.
7. In the **Attachment** field, the generated invoice is attached by default as a PDF file.
8. In the **Body** field, enter a short message to the recipient.

    If a document-specific email text is set up on the **Report Selection - Sales** page, then the **Body** field is filled in automatically. For more information, see [Set Up Reusable Email Texts and Layouts for Sales and Purchase Documents](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts-for-sales-and-purchase-documents).
9. Choose the **OK** button to send the email message.

> [!NOTE]  
> If you do not want to specify email settings each time you email a document, you can select the **Yes (Use Default Settings)** option in the **Email** field on the **Send Document to** page. In that case, the **Send Email** page will not open. See Step 4. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).  

## To compose and send an email
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Accounts**, and then choose the related link.
2. Choose the account to send the email from, and then choose the **Compose Email** action.

## Documents marked as printed when they are sent
Some documents in [!INCLUDE[prod_short](includes/prod_short.md)] have a field that specifies how many times the document has been printed. The number in that field <!--"that field?" need a name...--> is also updated if you send the document by email because a PDF file is generated for it. The number is updated even if you don't send the email. <!--guessing this is because emails are technically reports, so the counter bumps up whenever someone creates an email. Need to verify.-->

## Sent Emails and Your Email Outbox
[!INCLUDE[prod_short](includes/prod_short.md)] stores the emails that you send on the **Sent Items** page. That's to let you resend emails, or forward them to someone else. If you can't find an email in your sent items, look for it on the **Email Outbox** page. 

> [!NOTE]
> Depending on the extension that your company uses for email, administrators can see a list of messages that everyone has sent, but not the content of the messages

The **Email Outbox** is where you'll find the emails that you saved as drafts, and emails that failed to send, for example, if the email address was invalid. For messages that failed to send, you can choose **Show Error** or **Investigate Error** to troubleshoot the problem.

## See Also
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Set up Email](admin-how-setup-email.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
