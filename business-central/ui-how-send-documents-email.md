---
title: Set Up Document-Specific Email Content | Microsoft Docs
description: You can define content to insert into the body of an email message, for example, a PayPal link. You can also attach documents to email messages.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Office 365, cover, body, PayPal, layout
ms.date: 04/01/2020
ms.author: sgroespe

---
# Send Documents by Email
To communicate the contents of business documents quickly to your business partners, such as the payment information on sales documents to customers, you can use the Report Layout feature to define document-specific content that gets inserted in email bodies automatically. For more information, see [Managing Report and Document Layouts](ui-manage-report-layouts.md).

To enable emails from within [!INCLUDE[d365fin](includes/d365fin_md.md)], start the **Set Up Email** assisted setup guide on the Role Center.

You can email practically all document types as attachments to email messages directly from the page that shows the document. In addition to the attachment, you can set up document-specific email bodies with core information from the document preceded by standard text that greets the mail recipient and introduces the document in question. To offer your customers to pay for sales electronically using a payment service, such as PayPal, you can also have the PayPal information and hyperlink inserted in the email body.

From all supported documents, you initiate emailing by choosing the **Send** action, on posted documents, or the **Post and Send** action, on non-posted documents.

If the **Email** field on the **Send Document to** page is set to **Yes (Prompt for Settings)**, then the **Send Email** page opens prefilled with the contact person in the **To:** field and the document attached as a PDF file. In the **Body** field, you can either enter text manually or you can have the field filled with a document-specific email body that you have set up.

The following procedure describes how to set the **Sales - Invoice** report up to be used for document-specific email bodies when you email posted sales invoices.

## To set up a document-specific email body for sales invoices
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selections Sales**, and then choose the related link.
2. On the **Report Selection - Sales** page, in the **Usage** field, select **Invoice**.
3. On a new line, in the **Report ID** field, select, for example, standard report 1306.
4. Select the **Use for Email Body** check box.
5. Choose the **Email Body Layout Code** field, and then select a layout from the drop-down list.

    Report layouts define both the style and the content of the email body, including the standard text that precedes the core document information in the email body. You can see all available report layouts if you choose the **Select from full list** button in the drop-down list.
6. To view or edit the layout that the email body is based on, select the layout on the **Custom Report Layouts** page, and then choose the **Edit Layout** action.
7. If you want to offer customers to pay for sales electronically, you can set up the related payment service, such as PayPal, and then have the PayPal information and hyperlink inserted in the email body as well. For more information, see [Enable Customer Payments Through PayPal](sales-how-enable-payment-service-extensions.md).
8. Choose the **OK** button.

Now, when you choose, for example, the **Send** action on the **Posted Sales Invoice** page, the email body will contain the document information of report 1306 preceded by styled standard text according to the report layout that you selected in step 5.

The following procedure describes how to send a posted sales invoice as an email message with the document attached as a PDF file and with a document-specific email body.

## To send documents by email
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.
2. Select the relevant posted sales invoice, and then choose the **Send** action. The **Send Document to** page opens.
3. In the **Email** field, select **Yes (Prompt for Settings)**. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).
4. Choose the **OK** button. The **Send Email** page opens.
5. In the **To:** field, enter a valid email address. The default value is the customer email address.
6. In the **Subject** field, enter a descriptive subject text. The default value is the customer name and invoice number.
7. In the **Attachment** field, the generated invoice is attached by default as a PDF file.
8. In the **Body** field, enter a short message to the recipient.

    If a document-specific email body is set up on the **Report Selection - Sales** page, then the **Body** field is filled in automatically. For more information, see [To set up a document-specific email body for sales invoices](ui-how-send-documents-email.md#to-set-up-a-document-specific-email-body-for-sales-invoices).
9. Choose the **OK** button to send the email message.

> [!NOTE]  
>   If you do not want to specify email settings each time you email a document, you can select the **Yes (Use Default Settings)** option in the **Email** field on the **Send Document to** page. In that case, the **Send Email** page will not open. See Step 4. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

## See Also
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Set up Email](admin-how-setup-email.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
